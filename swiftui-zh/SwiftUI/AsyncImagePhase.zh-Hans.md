--- 来源：https://developer.apple.com/documentation/SwiftUI/AsyncImagePhase
抓取时间：2025-12-02T17:35:50Z

---

# AsyncImagePhase

**Enumeration**

异步图像加载操作的当前阶段。

## 声明

```swift
enum AsyncImagePhase
```

## 概述

当您使用 [init(url:scale:transaction:content:)](AsyncImage/init_url_scale_transaction_content.zh-Hans.md) 初始化器创建 [AsyncImage](AsyncImage.zh-Hans.md) 实例时，您可以使用 `content` 闭包定义视图的外观。SwiftUI 会在加载操作的不同阶段调用此闭包并传入一个阶段值，以指示当前状态。使用此阶段值来决定要绘制的内容。例如，您可以绘制已加载的图像（如果存在）、指示错误的视图或占位符：

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png")) { phase in
    if let image = phase.image {
        image // Displays the loaded image.
    } else if phase.error != nil {
        Color.red // Indicates an error.
    } else {
        Color.blue // Acts as a placeholder.
    }
}
```

## 获取加载阶段

- **AsyncImagePhase.empty**：未加载任何图像。

- **AsyncImagePhase.success(_:)**：图像已成功加载。

- **AsyncImagePhase.failure(_:)**：图像加载失败并出现错误。

## 获取图像

- **image**：已加载的图像（如有）。

## 获取错误

- **error**：尝试加载图像时发生的错误（如有）。

## 异步加载图像

- **AsyncImage**：异步加载并显示图像的视图。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/AsyncImagePhase
crawled: 2025-12-02T17:35:50Z
---

# AsyncImagePhase

**Enumeration**

The current phase of the asynchronous image loading operation.

## Declaration

```swift
enum AsyncImagePhase
```

## Overview

When you create an [AsyncImage](AsyncImage.zh-Hans.md) instance with the [init(url:scale:transaction:content:)](AsyncImage/init_url_scale_transaction_content.zh-Hans.md) initializer, you define the appearance of the view using a `content` closure. SwiftUI calls the closure with a phase value at different points during the load operation to indicate the current state. Use the phase to decide what to draw. For example, you can draw the loaded image if it exists, a view that indicates an error, or a placeholder:

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png")) { phase in
    if let image = phase.image {
        image // Displays the loaded image.
    } else if phase.error != nil {
        Color.red // Indicates an error.
    } else {
        Color.blue // Acts as a placeholder.
    }
}
```

## Getting load phases

- **AsyncImagePhase.empty**: No image is loaded.
- **AsyncImagePhase.success(_:)**: An image successfully loaded.
- **AsyncImagePhase.failure(_:)**: An image failed to load with an error.

## Getting the image

- **image**: The loaded image, if any.

## Getting the error

- **error**: The error that occurred when attempting to load an image, if any.

## Loading images asynchronously

- **AsyncImage**: A view that asynchronously loads and displays an image.

## Conforms To

- Sendable
- SendableMetatype

