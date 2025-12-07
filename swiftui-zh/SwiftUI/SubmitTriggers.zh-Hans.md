---
来源： https://developer.apple.com/documentation/SwiftUI/SubmitTriggers
抓取时间： 2025-12-02T17:42:10Z
---

# 提交触发器

**Structure**

定义各种触发器的类型，这些触发器会触发提交操作。

## 声明

```swift
struct SubmitTriggers
```

## 概览

这些触发器可提供给 [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) 修改器，以改变哪类用户行为会触发所提供的提交操作。

## 获取提交触发器

- **search**：定义来自由可搜索修饰符构建的搜索字段的触发器。
- **text**：定义源自文本输入控件（如 `TextField` 和 `SecureField`）的触发器。

## 创建一组选项

- **init(rawValue:)**：创建一组提交触发器。

## 响应提交事件

- **onSubmit(of:_:)**：添加当用户向该视图提交值时要执行的操作。
- **submitScope(_:)**：防止源于此视图的提交触发器调用由视图层次结构中更高层提交修改器配置的提交操作。

## 符合

- 等价
- 可表达数组字素
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/SubmitTriggers
crawled: 2025-12-02T17:42:10Z
---

# SubmitTriggers

**Structure**

A type that defines various triggers that result in the firing of a submission action.

## Declaration

```swift
struct SubmitTriggers
```

## Overview

These triggers may be provided to the [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) modifier to alter which types of user behaviors trigger a provided submission action.

## Getting submit triggers

- **search**: Defines triggers originating from search fields constructed from searchable modifiers.
- **text**: Defines triggers originating from text input controls like `TextField` and `SecureField`.

## Creating a set of options

- **init(rawValue:)**: Creates a set of submit triggers.

## Responding to submission events

- **onSubmit(of:_:)**: Adds an action to perform when the user submits a value to this view.
- **submitScope(_:)**: Prevents submission triggers originating from this view to invoke a submission action configured by a submission modifier higher up in the view hierarchy.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

