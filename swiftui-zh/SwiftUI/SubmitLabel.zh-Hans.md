--- 来源：https://developer.apple.com/documentation/SwiftUI/SubmitLabel
抓取时间：2025-12-02T17:42:11Z

---

# SubmitLabel

**Structure**

语义标签，用于描述视图层级结构中的提交操作。

## 声明

```swift
struct SubmitLabel
```

## 概述

提交标签是对视图层级结构中提交操作的描述，使用 [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) 修饰符。

## 获取提交标签

- **continue**：定义一个文本为“继续”的提交标签。

- **done**：定义一个文本为“完成”的提交标签。

- **go**：定义一个提交标签，文本为“Go”。

- **join**：定义一个提交标签，文本为“Join”。

- **next**：定义一个提交标签，文本为“Next”。

- **return**：定义一个提交标签，文本为“Return”。

- **route**：定义一个提交标签，文本为“Route”。

- **search**：定义一个提交标签，文本为“Search”。

- **send**：定义一个提交标签，文本为“Send”。

## 为提交事件添加标签

- **submitLabel(_:)**：设置此视图的提交标签。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SubmitLabel
crawled: 2025-12-02T17:42:11Z
---

# SubmitLabel

**Structure**

A semantic label describing the label of submission within a view hierarchy.

## Declaration

```swift
struct SubmitLabel
```

## Overview

A submit label is a description of a submission action provided to a view hierarchy using the [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) modifier.

## Getting submission labels

- **continue**: Defines a submit label with text of “Continue”.
- **done**: Defines a submit label with text of “Done”.
- **go**: Defines a submit label with text of “Go”.
- **join**: Defines a submit label with text of “Join”.
- **next**: Defines a submit label with text of “Next”.
- **return**: Defines a submit label with text of “Return”.
- **route**: Defines a submit label with text of “Route”.
- **search**: Defines a submit label with text of “Search”.
- **send**: Defines a submit label with text of “Send”.

## Labeling a submission event

- **submitLabel(_:)**: Sets the submit label for this view.

## Conforms To

- Sendable
- SendableMetatype

