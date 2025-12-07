---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/horizontalScrollBounceBehavior
抓取时间： 2025-12-02T17:40:44Z
---

# 水平滚动弹跳行为

**实例属性**

可滚动视图水平轴的滚动反弹模式。

## 声明

```swift
var horizontalScrollBounceBehavior: ScrollBounceBehavior { get set }
```

## 讨论

使用 [scrollBounceBehavior(_:axes:)](../View/scrollBounceBehavior___axes.zh-Hans.md) 视图修改器在 [Environment](../Environment.zh-Hans.md) 中设置此值。

## 配置滚动弹跳行为

- **scrollBounceBehavior(_:axes:)**：配置沿指定轴滚动视图的弹跳行为。
- **verticalScrollBounceBehavior**：可滚动视图垂直轴的滚动弹跳模式。
- **ScrollBounceBehavior**：可滚动视图在内容结束时的反弹方式。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/horizontalScrollBounceBehavior
crawled: 2025-12-02T17:40:44Z
---

# horizontalScrollBounceBehavior

**Instance Property**

The scroll bounce mode for the horizontal axis of scrollable views.

## Declaration

```swift
var horizontalScrollBounceBehavior: ScrollBounceBehavior { get set }
```

## Discussion

Use the [scrollBounceBehavior(_:axes:)](../View/scrollBounceBehavior___axes.zh-Hans.md) view modifier to set this value in the [Environment](../Environment.zh-Hans.md).

## Configuring scroll bounce behavior

- **scrollBounceBehavior(_:axes:)**: Configures the bounce behavior of scrollable views along the specified axis.
- **verticalScrollBounceBehavior**: The scroll bounce mode for the vertical axis of scrollable views.
- **ScrollBounceBehavior**: The ways that a scrollable view can bounce when it reaches the end of its content.

