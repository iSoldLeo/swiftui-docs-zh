--- 来源：https://developer.apple.com/documentation/swiftui/uihostingornament
抓取时间：2025-12-04T13:47:44Z

---

# UIHostingOrnament

**Class**

一个表示适合在 UIKit 中托管的装饰元素的模型。

## 声明

```swift
class UIHostingOrnament<Content> where Content : View
```

## 概述

当您想要向 UIKit 视图控制器添加装饰元素时，请使用 `UIHostingOrnament`。例如，以下代码会向当前视图控制器添加一个底部装饰元素：

```swift
self.ornaments = [
    UIHostingOrnament(sceneAnchor: .bottom) {
        OrnamentContent()
    }
]
```

## 创建托管装饰元素

- **init(sceneAnchor:contentAlignment:content:)**：创建一个具有指定对齐方式和内容的装饰元素。

- **rootView**：此装饰器管理的 SwiftUI 视图层级的根视图。

## 设置对齐方式

- **contentAlignment**：用于定位装饰器的对齐方式。

- **sceneAnchor**：用于将装饰器内容（基于 `contentAlignment`）与场景对齐的锚点。

## 实例属性

- **contentAlignment3D**

## 在 UIKit 中托管装饰器

- **UIOrnament**：表示装饰器的抽象基类。

## 继承自

- UIOrnament

## 符合以下协议

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/uihostingornament
crawled: 2025-12-04T13:47:44Z
---

# UIHostingOrnament

**Class**

A model that represents an ornament suitable for being hosted in UIKit.

## Declaration

```swift
class UIHostingOrnament<Content> where Content : View
```

## Overview

Use a `UIHostingOrnament` when you want to add ornaments to a UIKit view controller. For example, the following adds a single bottom ornament to the current view controller:

```swift
self.ornaments = [
    UIHostingOrnament(sceneAnchor: .bottom) {
        OrnamentContent()
    }
]
```

## Creating a hosting ornament

- **init(sceneAnchor:contentAlignment:content:)**: Creates an ornament with the specified alignment and content.
- **rootView**: The root view of the SwiftUI view hierarchy managed by this ornament.

## Setting the alignment

- **contentAlignment**: The alignment in the ornament used to position it.
- **sceneAnchor**: The anchor point for aligning the ornament’s content (based on the `contentAlignment`) with the scene.

## Instance Properties

- **contentAlignment3D**

## Hosting an ornament in UIKit

- **UIOrnament**: The abstract base class that represents an ornament.

## Inherits From

- UIOrnament

## Conforms To

- Sendable
- SendableMetatype

