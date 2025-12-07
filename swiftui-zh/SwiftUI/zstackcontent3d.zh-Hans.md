---
来源： https://developer.apple.com/documentation/swiftui/zstackcontent3d
抓取时间： 2025-12-04T11:36:13Z
---

# ZStackContent3D

**Structure**

为[ZStack](ZStack.zh-Hans.md)添加间距的类型。

## 声明

```swift
@frozen struct ZStackContent3D<Content> where Content : View
```

## 概览

您不会直接创建此类型。当您使用 `ZStack(alignment:spacing:content)` 初始化器时，SwiftUI 会为您创建它。

## 初始化器

- **init(spacing:content:)**

## 实例属性

- **content**
- **spacing**

## 符合

- 可复制
- 查看


---
source: https://developer.apple.com/documentation/swiftui/zstackcontent3d
crawled: 2025-12-04T11:36:13Z
---

# ZStackContent3D

**Structure**

A type that adds spacing to a [ZStack](ZStack.zh-Hans.md).

## Declaration

```swift
@frozen struct ZStackContent3D<Content> where Content : View
```

## Overview

You don’t create this type directly. SwiftUI creates it for you when you use the `ZStack(alignment:spacing:content)` initializer.

## Initializers

- **init(spacing:content:)**

## Instance Properties

- **content**
- **spacing**

## Conforms To

- Copyable
- View

