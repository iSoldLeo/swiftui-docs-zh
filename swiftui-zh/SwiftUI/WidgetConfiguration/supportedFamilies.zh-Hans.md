---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/supportedFamilies(_:)
抓取时间： 2025-12-02T19:43:01Z
---

# supportedFamilies(_:)

**实例方法**

设置 widget 支持的尺寸。

## 声明

```swift
@MainActor @preconcurrency func supportedFamilies(_ families: [WidgetFamily]) -> some WidgetConfiguration

```

## 参数

- **families**：widget 支持的尺寸集。

## 返回值

支持您指定尺寸的 widget 配置。

## 设置外观

- **contentMarginsDisabled()**：禁用默认内容边距。
- **disfavoredLocations(_:for:)**：为 widget 设置不喜欢的位置。
- **containerBackgroundRemovable(_:)**：将 widget 的背景标记为可移动的修改器。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/supportedFamilies(_:)
crawled: 2025-12-02T19:43:01Z
---

# supportedFamilies(_:)

**Instance Method**

Sets the sizes that a widget supports.

## Declaration

```swift
@MainActor @preconcurrency func supportedFamilies(_ families: [WidgetFamily]) -> some WidgetConfiguration

```

## Parameters

- **families**: The set of sizes the widget supports.

## Return Value

A widget configuration that supports the sizes you specify.

## Setting the appearance

- **contentMarginsDisabled()**: Disable default content margins.
- **disfavoredLocations(_:for:)**: Sets the disfavored locations for a widget.
- **containerBackgroundRemovable(_:)**: A modifier that marks the background of a widget as removable.

