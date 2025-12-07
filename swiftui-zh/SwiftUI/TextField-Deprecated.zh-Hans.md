---

来源：https://developer.apple.com/documentation/SwiftUI/TextField-Deprecated
抓取时间：2025-12-02T17:51:48Z

---

# 已弃用的初始化器

**API 集合**

查看已弃用的文本字段初始化器。

## 概述

替换这些初始化器时，请使用视图修饰符来指定文本字段的更改和提交行为。使用 [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) 视图修饰符可获得 `onCommit` 参数提供的行为。使用 [focused(_:equals:)](View/focused___equals.zh-Hans.md) 和 [FocusState](FocusState.zh-Hans.md) 可获得 `onEditingChanged` 参数提供的行为。

## 创建带有字符串的文本字段

- **init(_:text:onEditingChanged:onCommit:)**：创建一个文本字段，其文本标签由本地化标题字符串生成。

- **init(_:text:onCommit:)**：创建一个文本字段，其文本标签由本地化标题字符串生成。

- **init(_:text:onEditingChanged:)**：创建一个文本字段，其文本标签由本地化标题字符串生成。

## 创建带有值的文本字段

- **init(_:value:formatter:onEditingChanged:onCommit:)**：创建一个绑定到任意类型 `V` 的实例。

- **init(_:value:formatter:onCommit:)**：创建一个绑定到任意类型 `V` 的实例。

- **init(_:value:formatter:onEditingChanged:)**：创建一个绑定到任意类型 `V` 的实例。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField-Deprecated
crawled: 2025-12-02T17:51:48Z
---

# Deprecated initializers

**API Collection**

Review deprecated text field initializers.

## Overview

Use view modifiers to specify change and commit behaviors for a text field when replacing these initializers. Use the [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) view modifier to get the behavior provided by the `onCommit` parameter. Use [focused(_:equals:)](View/focused___equals.zh-Hans.md) and [FocusState](FocusState.zh-Hans.md) to get the behavior provided by the `onEditingChanged` parameter.

## Creating a text field with a string

- **init(_:text:onEditingChanged:onCommit:)**: Creates a text field with a text label generated from a localized title string.
- **init(_:text:onCommit:)**: Creates a text field with a text label generated from a localized title string.
- **init(_:text:onEditingChanged:)**: Creates a text field with a text label generated from a localized title string.

## Creating a text field with a value

- **init(_:value:formatter:onEditingChanged:onCommit:)**: Create an instance which binds over an arbitrary type, `V`.
- **init(_:value:formatter:onCommit:)**: Create an instance which binds over an arbitrary type, `V`.
- **init(_:value:formatter:onEditingChanged:)**: Create an instance which binds over an arbitrary type, `V`.

