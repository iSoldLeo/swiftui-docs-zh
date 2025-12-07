---
来源： https://developer.apple.com/documentation/swiftui/tabbarminimizebehavior/automatic
抓取时间： 2025-12-03T05:59:51Z
---

# 自动

**类型属性**

根据周围环境自动确定行为。

## 声明

```swift
static let automatic: TabBarMinimizeBehavior
```

## 讨论

取决于平台：

- 在 iOS、iPadOS、tvOS 和 watchOS 上，标签栏不会最小化。
- 在 visionOS 上，当人们将视线移开时，标签栏会最小化。
- 在 macOS 上，当窗口空间缩小时，标签栏会最小化。


---
source: https://developer.apple.com/documentation/swiftui/tabbarminimizebehavior/automatic
crawled: 2025-12-03T05:59:51Z
---

# automatic

**Type Property**

Determine the behavior automatically based on the surrounding context.

## Declaration

```swift
static let automatic: TabBarMinimizeBehavior
```

## Discussion

The depends on the platform:

- On iOS, iPadOS, tvOS, and watchOS, the tab bar does not minimize.
- On visionOS, the tab bar minimizes when people look away from it.
- On macOS, the tab bar minimizes when the window has reduced space.

