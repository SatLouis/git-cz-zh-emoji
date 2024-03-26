# git-cz-zh-emoji(汉化Emoji版)

[![Greenkeeper badge](https://badges.greenkeeper.io/commitizen/git-cz-zh-emoji.svg)](https://greenkeeper.io/)

Status:
[![npm version](https://img.shields.io/npm/v/git-cz-zh-emoji.svg?style=flat-square)](https://www.npmjs.org/package/git-cz-zh-emoji)
[![npm downloads](https://img.shields.io/npm/dm/git-cz-zh-emoji.svg?style=flat-square)](http://npm-stat.com/charts.html?package=git-cz-zh-emoji&from=2015-08-01)
[![Build Status](https://img.shields.io/travis/commitizen/git-cz-zh-emoji.svg?style=flat-square)](https://travis-ci.org/commitizen/git-cz-zh-emoji)

> 基于`cz-conventional-changelog-zh`的基础修改的中文版，并扩展了一些日常工作中需要用到的提交类型

Part of the [commitizen](https://github.com/commitizen/cz-cli) family. Prompts for [conventional changelog](https://github.com/conventional-changelog/conventional-changelog-zh-emoji) standard.

## Install

```
pnpm add git-cz-zh-emoji -g
```


## Configuration

### 全局
```
echo '{ "path": "git-cz-zh-emoji" }' > ~/.czrc 
```

### package.json

与 commitizen 一样，您可以通过 `package.json` 的`config.commitizen`关键字来配置`git-cz-zh-emoji`。

```json5
{
// ...  default values
    "scripts":{
      ...
      "commit": "git-cz"
    },
    "config": {
        "commitizen": {
            "path": "git-cz-zh-emoji", // 如有问题可以设置此路径:./node_modules/git-cz-zh-emoji
            "disableScopeLowerCase": false,
            "disableSubjectLowerCase": false,
            "maxHeaderWidth": 100,
            "maxLineWidth": 100,
            "defaultType": "",
            "defaultScope": "",
            "defaultSubject": "",
            "defaultBody": "",
            "defaultIssues": "",
            "types": {
              ...
              "custom": {
                "description": "A new type",
                "title": "Custom Type"
              },
              ...
            }
        }
    }
// ...
}
```

### Environment variables

以下环境变量可用于覆盖任何默认配置，包括 `package.json`的配置

- CZ_TYPE = defaultType
- CZ_SCOPE = defaultScope
- CZ_SUBJECT = defaultSubject
- CZ_BODY = defaultBody
- CZ_MAX_HEADER_WIDTH = maxHeaderWidth
- CZ_MAX_LINE_WIDTH = maxLineWidth

### Commitlint

如果使用[commitlint](https://github.com/conventional-changelog/commitlint) js 库, “maxHeaderWidth”配置属性将默认为“header-max-length”规则的配置，而不是硬编码的值 100。这可以通过在`package.json`中设置“maxHeaderWidth”配置来完成或 CZ_MAX_HEADER_WIDTH 环境变量。

### Types

扩展了新的提示类型,通过 `package.json` 的`config.commitizen`关键字来配置的类型会和原有内置的类型合并

```
{
  "init": {
    "description": "初始化",
    "title": "Init",
    "emoji": "🎉"
  },
  "feat": {
    "description": "一个新功能",
    "title": "Features",
    "emoji": "✨"
  },
  "fix": {
    "description": "一个bug",
    "title": "Bug Fixes",
    "emoji": "🐞"
  },
  "docs": {
    "description": "文档增删改",
    "title": "Documentation",
    "emoji": "📃"
  },
  "delete": {
    "description": "删除文件",
    "title": "Delete Files"
  },
  "style": {
    "description": "样式修改(空白、格式、缺少分号等)",
    "title": "Styles",
    "emoji": "🌈"
  },
  "refactor": {
    "description": "既不修复bug也不添加新功能的更改",
    "title": "Code Refactoring",
    "emoji": "🦄"
  },
  "perf": {
    "description": "性能优化",
    "title": "Performance Improvements",
    "emoji": "🎈"
  },
  "test": {
    "description": "增加测试",
    "title": "Tests",
    "emoji": "🧪"
  },
  "build": {
    "description": "影响构建系统或外部依赖项的更改(示例范围:gulp、broccoli、npm)",
    "title": "Builds",
    "emoji": "🔧"
  },
  "ci": {
    "description": "对CI配置文件和脚本的更改(示例范围:Travis, Circle, BrowserStack, SauceLabs)",
    "title": "Continuous Integrations",
    "emoji": "🐎"
  },
  "chore": {
    "description": "除src目录或测试文件以外的修改",
    "title": "Chores",
    "emoji": "🐳"
  },
  "revert": {
    "description": "回退历史版本",
    "title": "Reverts",
    "emoji": "↩"
  },
  "conflict": {
    "description": "修改冲突",
    "title": "Conflict"
  },
  "font": {
    "description": "字体文件更新",
    "title": "Fonts"
  },
  "stash": {
    "description": "暂存文件",
    "title": "Stash Files"
  }
}

```
