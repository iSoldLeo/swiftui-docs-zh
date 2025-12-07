---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarTitleDisplayMode/automatic
抓取时间： 2025-12-03T06:05:17Z
---

# 自动

**类型属性**

自动模式。

## 声明

```swift
static var automatic: ToolbarTitleDisplayMode { get }
```

## 讨论

对于 iOS、iPadOS 或 tvOS 导航堆栈中的根内容，此行为将：

- 当配置了导航标题时，默认为[large](large.zh-Hans.md)。
- 当未提供导航标题时，默认为[inline](inline.zh-Hans.md)。

在所有平台中，推送到导航堆栈的内容将使用导航堆栈中已有内容的行为。这在 macOS 中没有影响。

## 获取显示模式

- **inline**：内联模式。
- **inlineLarge**：内联大号模式。
- **large**：大型模式。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarTitleDisplayMode/automatic
crawled: 2025-12-03T06:05:17Z
---

# automatic

**Type Property**

The automatic mode.

## Declaration

```swift
static var automatic: ToolbarTitleDisplayMode { get }
```

## Discussion

For root content in a navigation stack in iOS, iPadOS, or tvOS this behavior will:

- Default to [large](large.zh-Hans.md) when a navigation title is configured.
- Default to [inline](inline.zh-Hans.md) when no navigation title is provided.

In all platforms, content pushed onto a navigation stack will use the behavior of the content already on the navigation stack. This has no effect in macOS.

## Getting display modes

- **inline**: The inline mode.
- **inlineLarge**: The inline large mode.
- **large**: The large mode.

