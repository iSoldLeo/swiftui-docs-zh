--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityFocused(_:equals:)

抓取时间：2025-11-30T21:29:07Z

---

# accessibilityFocused(_:equals:)

**实例方法**

通过将辅助功能元素的焦点状态绑定到给定的状态值来修改此视图。

## 声明

```swift
nonisolated func accessibilityFocused<Value>(_ binding: AccessibilityFocusState<Value>.Binding, equals value: Value) -> some View where Value : Hashable

```

## 参数

- **binding**：要注册的状态绑定。当辅助功能焦点移动到已修改视图的辅助功能元素时，SwiftUI 会将绑定值设置为相应的匹配值。如果您以编程方式将状态值设置为匹配值，则辅助功能焦点会移动到已修改视图的辅助功能元素。如果辅助功能焦点离开与修改后的视图关联的辅助功能元素，SwiftUI 会将值设置为 `nil`；以编程方式将值设置为 `nil` 则会自动解除焦点。

- **value**：用于确定绑定是否应更改时要匹配的值。

## 返回值

修改后的视图。

## 控制焦点

- **accessibilityFocused(_:)**：通过将辅助功能元素的焦点状态绑定到给定的布尔值来修改此视图。

- **AccessibilityFocusState**：属性包装类型，可以读取和写入 SwiftUI 在任何活动的辅助功能技术（例如 VoiceOver）的焦点更改时更新的值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityFocused(_:equals:)
crawled: 2025-11-30T21:29:07Z
---

# accessibilityFocused(_:equals:)

**Instance Method**

Modifies this view by binding its accessibility element’s focus state to the given state value.

## Declaration

```swift
nonisolated func accessibilityFocused<Value>(_ binding: AccessibilityFocusState<Value>.Binding, equals value: Value) -> some View where Value : Hashable

```

## Parameters

- **binding**: The state binding to register. When accessibility focus moves to the accessibility element of the modified view, SwiftUI sets the bound value to the corresponding match value. If you set the state value programmatically to the matching value, then accessibility focus moves to the accessibility element of the modified view. SwiftUI sets the value to `nil` if accessibility focus leaves the accessibility element associated with the modified view, and programmatically setting the value to `nil` dismisses focus automatically.
- **value**: The value to match against when determining whether the binding should change.

## Return Value

The modified view.

## Controlling focus

- **accessibilityFocused(_:)**: Modifies this view by binding its accessibility element’s focus state to the given boolean state value.
- **AccessibilityFocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the focus of any active accessibility technology, such as VoiceOver, changes.

