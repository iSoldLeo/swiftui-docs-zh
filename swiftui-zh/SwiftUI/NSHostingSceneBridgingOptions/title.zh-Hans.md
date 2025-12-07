---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingSceneBridgingOptions/title
抓取时间： 2025-12-03T06:57:51Z
---

# 标题

**类型属性**

托管视图的相关窗口的标题和副标题将分别使用`navigationTitle(_:)` 和 `navigationSubtitle(_:)` 修改器提供的值填充。

### 声明

```swift
static let title: NSHostingSceneBridgingOptions
```

## 讨论

以这种方式填充的标题栏会覆盖使用 AppKit 设置的任何值。

## 获取桥接选项

- **all**：托管视图的关联窗口的标题栏和工具栏都将使用各自修改器的值填充。
- **toolbars**：托管视图的关联窗口将使用`toolbar(content:)` 修改器提供的任何项目填充工具栏。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingSceneBridgingOptions/title
crawled: 2025-12-03T06:57:51Z
---

# title

**Type Property**

The hosting view’s associated window will have its title and subtitle populated with the values provided to the `navigationTitle(_:)` and `navigationSubtitle(_:)` modifiers, respectively.

## Declaration

```swift
static let title: NSHostingSceneBridgingOptions
```

## Discussion

Title bars populated in this manner overwrite any values set using AppKit.

## Geting bridging options

- **all**: The hosting view’s associated window will have both its title bars and toolbars populated with values from their respective modifiers.
- **toolbars**: The hosting view’s associated window will have its toolbar populated with any items provided to the `toolbar(content:)` modifier.

