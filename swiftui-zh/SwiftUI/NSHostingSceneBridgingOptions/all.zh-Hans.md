---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingSceneBridgingOptions/all
抓取时间：2025-12-03T06:57:51Z
---

# 所有

**类型属性**

托管视图的相关窗口的标题栏和工具栏都将使用各自修改器的值填充。

### 声明

```swift
static let all: NSHostingSceneBridgingOptions
```

## 获取桥接选项

- **title**：托管视图的关联窗口的标题和副标题将分别使用`navigationTitle(_:)` 和 `navigationSubtitle(_:)`修改器提供的值填充。
- **toolbars**：托管视图的相关窗口的工具栏将填充`toolbar(content:)` 修改器提供的任何项目。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingSceneBridgingOptions/all
crawled: 2025-12-03T06:57:51Z
---

# all

**Type Property**

The hosting view’s associated window will have both its title bars and toolbars populated with values from their respective modifiers.

## Declaration

```swift
static let all: NSHostingSceneBridgingOptions
```

## Geting bridging options

- **title**: The hosting view’s associated window will have its title and subtitle populated with the values provided to the `navigationTitle(_:)` and `navigationSubtitle(_:)` modifiers, respectively.
- **toolbars**: The hosting view’s associated window will have its toolbar populated with any items provided to the `toolbar(content:)` modifier.

