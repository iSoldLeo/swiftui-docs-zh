---
来源： https://developer.apple.com/documentation/SwiftUI/ScenePadding
抓取时间： 2025-12-02T17:38:34Z
---

# ScenePadding

**Structure**

用于拉开视图与其包含的场景之间距离的填充。

## 声明

```swift
struct ScenePadding
```

## 概览

使用[scenePadding(_:edges:)](View/scenePadding___edges.zh-Hans.md)修饰符为视图添加场景填充。

## 获取填充值

- **minimum**：最小场景填充值。
- **navigationBar**：导航栏内容场景填充值。

## 在视图周围添加填充

- **padding(_:)**：为视图的每个边缘添加不同的填充量。
- **padding(_:_:)**：为该视图的特定边缘添加相等的填充量。
- **padding3D(_:)**：使用您指定的边缘嵌入对该视图进行填充。
- **padding3D(_:_:)**：使用您指定的边缘嵌套平铺此视图。
- **scenePadding(_:)**：使用适合当前场景的数量为该视图的指定边缘添加衬垫。
- **scenePadding(_:edges:)**：为该视图的指定边缘添加指定类型的填充，填充量应与当前场景相适应。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/ScenePadding
crawled: 2025-12-02T17:38:34Z
---

# ScenePadding

**Structure**

The padding used to space a view from its containing scene.

## Declaration

```swift
struct ScenePadding
```

## Overview

Add scene padding to a view using the [scenePadding(_:edges:)](View/scenePadding___edges.zh-Hans.md) modifier.

## Getting padding values

- **minimum**: The minimum scene padding value.
- **navigationBar**: The navigation bar content scene padding.

## Adding padding around a view

- **padding(_:)**: Adds a different padding amount to each edge of this view.
- **padding(_:_:)**: Adds an equal padding amount to specific edges of this view.
- **padding3D(_:)**: Pads this view using the edge insets you specify.
- **padding3D(_:_:)**: Pads this view using the edge insets you specify.
- **scenePadding(_:)**: Adds padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **scenePadding(_:edges:)**: Adds a specified kind of padding to the specified edges of this view using an amount that’s appropriate for the current scene.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

