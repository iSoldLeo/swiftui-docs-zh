---
来源： https://developer.apple.com/documentation/swiftui/immersiveenvironmentbehavior
抓取时间： 2025-12-03T05:33:36Z
---

# 沉浸式环境行为

**Structure**

当您的应用程序打开一个场景时，系统提供的沉浸式环境的行为。

## 声明

```swift
struct ImmersiveEnvironmentBehavior
```

## 概览

将其中一个值与[immersiveEnvironmentBehavior(_:)](scene/immersiveEnvironmentBehavior.zh-Hans.md) 场景修改器一起使用，可指示当您的应用程序打开一个场景时，沉浸式环境应如何运行。

## 类型属性

- **automatic**：与系统默认行为相匹配的行为。
- **coexist**：打开场景时保持系统沉浸式环境原样的行为。
- **replace**：用新场景替换当前打开的任何沉浸式环境的行为。

## 创建沉浸式空间

- **ImmersiveSpace**：在无边界空间中呈现内容的场景。
- **ImmersiveSpaceContentBuilder**：用于合成沉浸式空间元素集合的结果生成器。
- **immersionStyle(selection:in:)**：设置沉浸式空间的样式。
- **ImmersionStyle**：身临其境空间可具有的样式。
- **immersiveSpaceDisplacement**：将沉浸式空间从默认位置移开时，系统应用于该空间的位移（米）。
- **ProgressiveImmersionAspectRatio**

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/swiftui/immersiveenvironmentbehavior
crawled: 2025-12-03T05:33:36Z
---

# ImmersiveEnvironmentBehavior

**Structure**

The behavior of the system-provided immersive environments when a scene is opened by your app.

## Declaration

```swift
struct ImmersiveEnvironmentBehavior
```

## Overview

Use one of these values with the [immersiveEnvironmentBehavior(_:)](scene/immersiveEnvironmentBehavior.zh-Hans.md) scene modifier to indicate how the immersive environment should behave when your app opens a scene.

## Type Properties

- **automatic**: A behavior that matches the system default behavior.
- **coexist**: A behavior that keeps the system’s immersive environment as is when opening a scene.
- **replace**: A behavior that replaces any currently opened immersive environment with the new scene.

## Creating an immersive space

- **ImmersiveSpace**: A scene that presents its content in an unbounded space.
- **ImmersiveSpaceContentBuilder**: A result builder for composing a collection of immersive space elements.
- **immersionStyle(selection:in:)**: Sets the style for an immersive space.
- **ImmersionStyle**: The styles that an immersive space can have.
- **immersiveSpaceDisplacement**: The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.
- **ProgressiveImmersionAspectRatio**

## Conforms To

- Equatable
- Sendable
- SendableMetatype

