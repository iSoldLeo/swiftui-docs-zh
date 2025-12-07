---
来源： https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds
抓取时间： 2025-12-02T17:42:19Z
---

# ContentShapeKinds

**Structure**

视图内容形状的种类。

## 声明

```swift
struct ContentShapeKinds
```

## 概览

系统使用种类来影响各种效果、命中测试等。

## 获取形状种类

- **interaction**：用于命中测试和可访问性的形状。
- **dragPreview**：用于拖放预览。
- **contextMenuPreview**：用于上下文菜单预览的类型。
- **focusEffect**：用于焦点效果的类型。
- **hoverEffect**：用于悬停效果的类型。
- **accessibility**：用于无障碍视觉效果和排序。

## 创建一组选项

- **init(rawValue:)**：创建内容形状类型。

## 控制命中测试

- **allowsTightening(_:)**：设置该视图中的文本是否可以在必要时压缩字符之间的空格，以适应一行中的文本。
- **contentShape(_:eoFill:)**：定义命中测试的内容形状。
- **contentShape(_:_:eoFill:)**：设置此视图的内容形状。

## 符合

- 等价
- 可表达数组字形
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds
crawled: 2025-12-02T17:42:19Z
---

# ContentShapeKinds

**Structure**

A kind for the content shape of a view.

## Declaration

```swift
struct ContentShapeKinds
```

## Overview

The kind is used by the system to influence various effects, hit-testing, and more.

## Getting shape kinds

- **interaction**: The kind for hit-testing and accessibility.
- **dragPreview**: The kind for drag and drop previews.
- **contextMenuPreview**: The kind for context menu previews.
- **focusEffect**: The kind for the focus effect.
- **hoverEffect**: The kind for hover effects.
- **accessibility**: The kind for accessibility visuals and sorting.

## Creating a set of options

- **init(rawValue:)**: Creates a content shape kind.

## Controlling hit testing

- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **contentShape(_:eoFill:)**: Defines the content shape for hit testing.
- **contentShape(_:_:eoFill:)**: Sets the content shape for this view.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

