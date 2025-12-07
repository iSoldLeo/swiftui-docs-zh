--- 来源：https://developer.apple.com/documentation/swiftui/surroundingseffect
抓取时间：2025-12-03T06:08:43Z

---

# SurroundingsEffect

**Structure**

系统可应用于直通视频的效果。

## 声明

```swift
struct SurroundingsEffect
```

## 概述

将这些值之一与 [preferredSurroundingsEffect(_:)](View/preferredsurroundingseffect.zh-Hans.md) 视图修饰符一起使用，以指示在显示修改后的视图时，要应用于直通视频的效果。

## 获取效果

- **systemDark**：使直通视频变暗的效果。

## 类型属性

- **dark**：使直通视频变暗的效果。

- **semiDark**：一种将直通视频亮度降低至低于 [dark](SurroundingsEffect/dark.zh-Hans.md) 的效果。

- **ultraDark**：一种将直通视频亮度降低至高于 [dark](SurroundingsEffect/dark.zh-Hans.md) 的效果。

## 类型方法

- **colorMultiply(_:)**：一种通过将直通视频乘以 [Color](Color.zh-Hans.md) 来应用自定义色调的效果。

- **dim(intensity:)**：一种将直通视频亮度降低至自定义值的效果。

## 配置直通视频

- **preferredSurroundingsEffect(_:)**：将效果应用于直通视频。

- **BreakthroughEffect**

## 符合以下标准

- Equatable


---
source: https://developer.apple.com/documentation/swiftui/surroundingseffect
crawled: 2025-12-03T06:08:43Z
---

# SurroundingsEffect

**Structure**

Effects that the system can apply to passthrough video.

## Declaration

```swift
struct SurroundingsEffect
```

## Overview

Use one of these values with the [preferredSurroundingsEffect(_:)](View/preferredsurroundingseffect.zh-Hans.md) view modifier to indicate what effect to apply to passthrough video when the modified view is displayed.

## Getting the effect

- **systemDark**: An effect that dims passthrough video.

## Type Properties

- **dark**: An effect that dims passthrough video.
- **semiDark**: An effect that dims passthrough video less than [dark](SurroundingsEffect/dark.zh-Hans.md).
- **ultraDark**: An effect that dims passthrough video more than [dark](SurroundingsEffect/dark.zh-Hans.md)

## Type Methods

- **colorMultiply(_:)**: An effect that applies a custom tint to the passthrough video by multiplying the passthrough with a [Color](Color.zh-Hans.md).
- **dim(intensity:)**: An effect that dims the passthrough video a custom amount.

## Configuring passthrough

- **preferredSurroundingsEffect(_:)**: Applies an effect to passthrough video.
- **BreakthroughEffect**

## Conforms To

- Equatable

