--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollIndicatorsFlash(onAppear:)

抓取时间：2025-11-30T21:25:40Z

---

# scrollIndicatorsFlash(onAppear:)

**实例方法**

当可滚动视图出现时，使其滚动指示器闪烁。

## 声明

```swift
nonisolated func scrollIndicatorsFlash(onAppear: Bool) -> some View

```

## 参数

- **onAppear**：一个布尔值，指示滚动视图出现时是否闪烁滚动指示器。

## 返回值

一个视图，其所有可见的滚动指示器在首次出现时都会闪烁。

## 说明

使用此修饰符可以控制滚动视图首次出现时，其滚动指示器是否短暂闪烁。例如，您可以将 `onAppear` 参数设置为 `true`，使指示器闪烁：

```swift
ScrollView {
    // ...
}
.scrollIndicatorsFlash(onAppear: true)
```

只有您配置为可见的滚动指示器才会闪烁。要使滚动指示器在值更改时闪烁，请改用 [scrollIndicatorsFlash(trigger:)](scrollIndicatorsFlash_trigger.zh-Hans.md)。

## 显示滚动指示器

- **scrollIndicatorsFlash(trigger:)**：当值更改时，使可滚动视图的滚动指示器闪烁。

- **scrollIndicators(_:axes:)**：设置此视图中滚动指示器的可见性。

- **horizontalScrollIndicatorVisibility**：应用于任何水平滚动内容的滚动指示器的可见性。

- **verticalScrollIndicatorVisibility**：应用于任何垂直滚动内容的滚动指示器的可见性。

- **ScrollIndicatorVisibility**：用户界面元素滚动指示器的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollIndicatorsFlash(onAppear:)
crawled: 2025-11-30T21:25:40Z
---

# scrollIndicatorsFlash(onAppear:)

**Instance Method**

Flashes the scroll indicators of a scrollable view when it appears.

## Declaration

```swift
nonisolated func scrollIndicatorsFlash(onAppear: Bool) -> some View

```

## Parameters

- **onAppear**: A Boolean value that indicates whether the scroll indicators flash when the scroll view appears.

## Return Value

A view that flashes any visible scroll indicators when it first appears.

## Discussion

Use this modifier to control whether the scroll indicators of a scroll view briefly flash when the view first appears. For example, you can make the indicators flash by setting the `onAppear` parameter to `true`:

```swift
ScrollView {
    // ...
}
.scrollIndicatorsFlash(onAppear: true)
```

Only scroll indicators that you configure to be visible flash. To flash scroll indicators when a value changes, use [scrollIndicatorsFlash(trigger:)](scrollIndicatorsFlash_trigger.zh-Hans.md) instead.

## Showing scroll indicators

- **scrollIndicatorsFlash(trigger:)**: Flashes the scroll indicators of scrollable views when a value changes.
- **scrollIndicators(_:axes:)**: Sets the visibility of scroll indicators within this view.
- **horizontalScrollIndicatorVisibility**: The visibility to apply to scroll indicators of any horizontally scrollable content.
- **verticalScrollIndicatorVisibility**: The visiblity to apply to scroll indicators of any vertically scrollable content.
- **ScrollIndicatorVisibility**: The visibility of scroll indicators of a UI element.

