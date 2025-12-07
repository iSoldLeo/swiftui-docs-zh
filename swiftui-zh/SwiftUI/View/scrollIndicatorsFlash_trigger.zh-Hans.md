--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollIndicatorsFlash(trigger:)

抓取时间：2025-11-30T21:25:41Z

---

# scrollIndicatorsFlash(trigger:)

**实例方法**

当值发生变化时，可滚动视图的滚动指示器会闪烁。

## 声明

```swift
nonisolated func scrollIndicatorsFlash(trigger value: some Equatable) -> some View

```

## 参数

- **value**：使滚动指示器闪烁的值。该值必须符合 [doc://com.apple.documentation/documentation/Swift/Equatable] 协议。

## 返回值

一个视图，当值发生变化时，所有可见的滚动指示器都会闪烁。

## 说明

当您提供给此修饰符的值发生变化时，被修改视图层次结构中所有可滚动视图的滚动指示器都会短暂闪烁。以下示例配置滚动指示器，使其在 `flashCount` 发生变化时闪烁：

```swift
@State private var isPresented = false
@State private var flashCount = 0

ScrollView {
    // ...
}
.scrollIndicatorsFlash(trigger: flashCount)
.sheet(isPresented: $isPresented) {
    // ...
}
.onChange(of: isPresented) { newValue in
    if newValue {
        flashCount += 1
    }
}
```

只有您配置为可见的滚动指示器才会闪烁。要在滚动视图首次出现时闪烁滚动指示器，请改用 [scrollIndicatorsFlash(onAppear:)](scrollIndicatorsFlash_onAppear.zh-Hans.md)。

## 显示滚动指示器

- **scrollIndicatorsFlash(onAppear:)**：在可滚动视图出现时闪烁其滚动指示器。

- **scrollIndicators(_:axes:)**：设置此视图中滚动指示器的可见性。

- **horizontalScrollIndicatorVisibility**：应用于任何水平可滚动内容的滚动指示器的可见性。

- **verticalScrollIndicatorVisibility**：应用于任何垂直可滚动内容的滚动指示器的可见性。

- **ScrollIndicatorVisibility**：UI 元素的滚动指示器的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollIndicatorsFlash(trigger:)
crawled: 2025-11-30T21:25:41Z
---

# scrollIndicatorsFlash(trigger:)

**Instance Method**

Flashes the scroll indicators of scrollable views when a value changes.

## Declaration

```swift
nonisolated func scrollIndicatorsFlash(trigger value: some Equatable) -> some View

```

## Parameters

- **value**: The value that causes scroll indicators to flash. The value must conform to the [doc://com.apple.documentation/documentation/Swift/Equatable] protocol.

## Return Value

A view that flashes any visible scroll indicators when a value changes.

## Discussion

When the value that you provide to this modifier changes, the scroll indicators of any scrollable views within the modified view hierarchy briefly flash. The following example configures the scroll indicators to flash any time `flashCount` changes:

```swift
@State private var isPresented = false
@State private var flashCount = 0

ScrollView {
    // ...
}
.scrollIndicatorsFlash(trigger: flashCount)
.sheet(isPresented: $isPresented) {
    // ...
}
.onChange(of: isPresented) { newValue in
    if newValue {
        flashCount += 1
    }
}
```

Only scroll indicators that you configure to be visible flash. To flash scroll indicators when a scroll view initially appears, use [scrollIndicatorsFlash(onAppear:)](scrollIndicatorsFlash_onAppear.zh-Hans.md) instead.

## Showing scroll indicators

- **scrollIndicatorsFlash(onAppear:)**: Flashes the scroll indicators of a scrollable view when it appears.
- **scrollIndicators(_:axes:)**: Sets the visibility of scroll indicators within this view.
- **horizontalScrollIndicatorVisibility**: The visibility to apply to scroll indicators of any horizontally scrollable content.
- **verticalScrollIndicatorVisibility**: The visiblity to apply to scroll indicators of any vertically scrollable content.
- **ScrollIndicatorVisibility**: The visibility of scroll indicators of a UI element.

