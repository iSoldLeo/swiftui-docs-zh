--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentedWindowContent
抓取时间：2025-12-02T17:27:37Z

---

# PresentedWindowContent

**Structure**

一个表示已呈现窗口内容的视图。

## 声明

```swift
struct PresentedWindowContent<Data, Content> where Data : Decodable, Data : Encodable, Data : Hashable, Content : View
```

## 概述

您不能直接创建此类型。[WindowGroup](WindowGroup.zh-Hans.md) 会自动为您创建值。

## 符合以下类型：

- View


---
source: https://developer.apple.com/documentation/SwiftUI/PresentedWindowContent
crawled: 2025-12-02T17:27:37Z
---

# PresentedWindowContent

**Structure**

A view that represents the content of a presented window.

## Declaration

```swift
struct PresentedWindowContent<Data, Content> where Data : Decodable, Data : Encodable, Data : Hashable, Content : View
```

## Overview

You don’t create this type directly. [WindowGroup](WindowGroup.zh-Hans.md) creates values for you.

## Conforms To

- View

