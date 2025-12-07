---
来源： https://developer.apple.com/documentation/swiftui/immersivespacecontentbuilder
抓取时间： 2025-12-03T05:33:33Z
---

# 沉浸式空间内容生成器

**Structure**

用于合成沉浸式空间元素集合的结果生成器。

## 声明

```swift
@resultBuilder struct ImmersiveSpaceContentBuilder
```

## 建设内容

- **buildBlock(_:)**

## 创建身临其境的空间

- **ImmersiveSpace**：在无边界空间中呈现内容的场景。
- **immersionStyle(selection:in:)**：设置沉浸式空间的风格。
- **ImmersionStyle**：身临其境空间可具有的样式。
- **immersiveSpaceDisplacement**：将沉浸式空间从默认位置移开时，系统应用于该空间的位移（米）。
- **ImmersiveEnvironmentBehavior**：当您的应用程序打开场景时，系统提供的沉浸式环境的行为。
- **ProgressiveImmersionAspectRatio**：当您的应用程序打开场景时，系统提供的沉浸式环境的行为。


---
source: https://developer.apple.com/documentation/swiftui/immersivespacecontentbuilder
crawled: 2025-12-03T05:33:33Z
---

# ImmersiveSpaceContentBuilder

**Structure**

A result builder for composing a collection of immersive space elements.

## Declaration

```swift
@resultBuilder struct ImmersiveSpaceContentBuilder
```

## Building content

- **buildBlock(_:)**

## Creating an immersive space

- **ImmersiveSpace**: A scene that presents its content in an unbounded space.
- **immersionStyle(selection:in:)**: Sets the style for an immersive space.
- **ImmersionStyle**: The styles that an immersive space can have.
- **immersiveSpaceDisplacement**: The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.
- **ImmersiveEnvironmentBehavior**: The behavior of the system-provided immersive environments when a scene is opened by your app.
- **ProgressiveImmersionAspectRatio**

