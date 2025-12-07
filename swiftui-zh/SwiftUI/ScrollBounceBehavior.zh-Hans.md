---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollBounceBehavior
抓取时间： 2025-12-02T17:40:45Z
---

# 滚动反弹行为

**Structure**

可滚动视图在内容结束时反弹的方式。

## 声明

```swift
struct ScrollBounceBehavior
```

## 概览

使用[scrollBounceBehavior(_:axes:)](View/scrollBounceBehavior___axes.zh-Hans.md)视图修改器可为可滚动视图（如[ScrollView](ScrollView.zh-Hans.md)或[List](List.zh-Hans.md)）设置此类值。该值用于配置当用户滚动到视图内容末尾时的跳转行为。

您可以配置每个可滚动轴使用不同的跳转模式。

## 反弹行为

- **automatic**：自动行为。
- **always**：自动行为：滚动视图总是跳动。
- **basedOnSize**：自动行为：当内容大到需要滚动时，滚动视图会弹起。

## 配置滚动弹起行为

- **scrollBounceBehavior(_:axes:)**：配置沿指定轴滚动视图的弹跳行为。
- **horizontalScrollBounceBehavior**：可滚动视图水平轴的滚动弹跳模式。
- **verticalScrollBounceBehavior**：可滚动视图垂直轴的滚动弹跳模式。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollBounceBehavior
crawled: 2025-12-02T17:40:45Z
---

# ScrollBounceBehavior

**Structure**

The ways that a scrollable view can bounce when it reaches the end of its content.

## Declaration

```swift
struct ScrollBounceBehavior
```

## Overview

Use the [scrollBounceBehavior(_:axes:)](View/scrollBounceBehavior___axes.zh-Hans.md) view modifier to set a value of this type for a scrollable view, like a [ScrollView](ScrollView.zh-Hans.md) or a [List](List.zh-Hans.md). The value configures the bounce behavior when people scroll to the end of the view’s content.

You can configure each scrollable axis to use a different bounce mode.

## Bounce behaviors

- **automatic**: The automatic behavior.
- **always**: The scrollable view always bounces.
- **basedOnSize**: The scrollable view bounces when its content is large enough to require scrolling.

## Configuring scroll bounce behavior

- **scrollBounceBehavior(_:axes:)**: Configures the bounce behavior of scrollable views along the specified axis.
- **horizontalScrollBounceBehavior**: The scroll bounce mode for the horizontal axis of scrollable views.
- **verticalScrollBounceBehavior**: The scroll bounce mode for the vertical axis of scrollable views.

## Conforms To

- Sendable
- SendableMetatype

