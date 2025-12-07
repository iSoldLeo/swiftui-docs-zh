--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollInputBehavior(_:for:)

抓取时间：2025-11-30T21:10:24Z

---

# scrollInputBehavior(_:for:)

**实例方法**

启用或禁用可滚动视图中特定输入框的滚动功能。

## 声明

```swift
@MainActor @preconcurrency func scrollInputBehavior(_ behavior: ScrollInputBehavior, for input: ScrollInputKind) -> some View

```

## 参数

- **behavior**：是否启用或禁用此输入框的滚动功能。

- **input**：要启用或禁用滚动功能的输入框。

## 说明

与 [scrollDisabled(_:)](scrollDisabled.zh-Hans.md) 不同，此修饰符仅针对特定输入框启用或禁用滚动功能。例如，以下代码会在 watchOS 上禁用双击滚动功能，同时保留通过触摸和数码表冠滚动的功能：

```swift
ScrollView(...)
    .scrollInputBehavior(.disabled, for: .handGestureShortcut)
```

如果已将 `scrollDisabled(true)` 应用于此视图，则所有输入方式的滚动功能都将被禁用，并且无法使用此修饰符重新启用滚动功能。

## 管理不同输入方式的滚动

- **ScrollInputKind**：用于滚动视图的输入方式。

- **ScrollInputBehavior**：定义输入方式是否应滚动视图的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollInputBehavior(_:for:)
crawled: 2025-11-30T21:10:24Z
---

# scrollInputBehavior(_:for:)

**Instance Method**

Enables or disables scrolling in scrollable views when using particular inputs.

## Declaration

```swift
@MainActor @preconcurrency func scrollInputBehavior(_ behavior: ScrollInputBehavior, for input: ScrollInputKind) -> some View

```

## Parameters

- **behavior**: Whether scrolling should be enabled or disabled for this input.
- **input**: The input for which to enable or disable scrolling.

## Discussion

In contrast to [scrollDisabled(_:)](scrollDisabled.zh-Hans.md), this modifier will enable or disable scrolling only for particular inputs. The following, for instance, disables double-tap-to-scroll on watchOS while preserving the ability to scroll via touch and the Digital Crown:

```swift
ScrollView(...)
    .scrollInputBehavior(.disabled, for: .handGestureShortcut)
```

If `scrollDisabled(true)` has been applied to this view, scrolling will be disabled for all inputs and this modifier cannot be used to re-enable scrolling.

## Managing scrolling for different inputs

- **ScrollInputKind**: Inputs used to scroll views.
- **ScrollInputBehavior**: A type that defines whether input should scroll a view.

