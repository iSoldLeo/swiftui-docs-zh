--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityFocused(_:)

抓取时间：2025-11-30T21:29:06Z

---

# accessibilityFocused(_:)

**实例方法**

通过将辅助功能元素的焦点状态绑定到给定的布尔值来修改此视图。

## 声明

```swift
nonisolated func accessibilityFocused(_ condition: AccessibilityFocusState<Bool>.Binding) -> some View

```

## 参数

- **condition**：要绑定的辅助功能焦点状态。当辅助功能焦点移动到已修改视图的辅助功能元素时，焦点值将设置为 `true`。如果以编程方式将该值设置为 `true`，则辅助功能焦点将移动到已修改视图的辅助功能元素。如果辅助功能焦点离开已修改视图的辅助功能元素，则该值将设置为 `false`；如果通过编程方式将该值设置为 `false`，则辅助功能焦点将自动消失。

## 返回值

已修改的视图。

## 控制焦点

- **accessibilityFocused(_:equals:)**：通过将辅助功能元素的焦点状态绑定到给定的状态值来修改此视图。

- **AccessibilityFocusState**：属性包装类型，可以读取和写入 SwiftUI 在任何活动的辅助功能技术（例如 VoiceOver）的焦点更改时更新的值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityFocused(_:)
crawled: 2025-11-30T21:29:06Z
---

# accessibilityFocused(_:)

**Instance Method**

Modifies this view by binding its accessibility element’s focus state to the given boolean state value.

## Declaration

```swift
nonisolated func accessibilityFocused(_ condition: AccessibilityFocusState<Bool>.Binding) -> some View

```

## Parameters

- **condition**: The accessibility focus state to bind. When accessibility focus moves to the accessibility element of the modified view, the focus value is set to `true`. If the value is set to `true` programmatically, then accessibility focus will move to accessibility element of the modified view. The value will be set to `false` if accessibility focus leaves the accessibility element of the modified view, and accessibility focus will be dismissed automatically if the value is set to `false` programmatically.

## Return Value

The modified view.

## Controlling focus

- **accessibilityFocused(_:equals:)**: Modifies this view by binding its accessibility element’s focus state to the given state value.
- **AccessibilityFocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the focus of any active accessibility technology, such as VoiceOver, changes.

