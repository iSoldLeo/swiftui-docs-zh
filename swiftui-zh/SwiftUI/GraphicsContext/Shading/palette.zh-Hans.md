---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/palette(_:)
抓取时间： 2025-12-01T22:05:09Z
---

# 调色板(_:)

**类型方法**

返回由着色实例数组构建的多级着色实例。

## 声明

```swift
static func palette(_ array: [GraphicsContext.Shading]) -> GraphicsContext.Shading
```

## 参数

- **array**：着色实例数组。数组必须至少包含一个元素。

## 返回值

由给定实例组成的阴影实例。

## 复合阴影类型

- **backdrop**：绘制当前背景副本的阴影实例。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/palette(_:)
crawled: 2025-12-01T22:05:09Z
---

# palette(_:)

**Type Method**

Returns a multilevel shading instance constructed from an array of shading instances.

## Declaration

```swift
static func palette(_ array: [GraphicsContext.Shading]) -> GraphicsContext.Shading
```

## Parameters

- **array**: An array of shading instances. The array must contain at least one element.

## Return Value

A shading instance composed from the given instances.

## Composite shading types

- **backdrop**: A shading instance that draws a copy of the current background.

