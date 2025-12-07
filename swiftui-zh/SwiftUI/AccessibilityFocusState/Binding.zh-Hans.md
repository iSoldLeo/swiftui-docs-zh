---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityFocusState/Binding
抓取时间： 2025-12-03T06:49:24Z
---

# AccessibilityFocusState.Binding | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ AccessibilityFocusState ](/documentation/swiftui/accessibilityfocusstate)

- [ 辅助功能焦点状态绑定 ](/documentation/SwiftUI/AccessibilityFocusState/Binding)

- [ 辅助功能焦点状态 ](/documentation/swiftui/accessibilityfocusstate)

- 无障碍焦点状态绑定

结构# AccessibilityFocusState.Binding

iOS 15.0+iPadOS 15.0+Mac Catalyst 15.0+macOS 12.0+tvOS 15.0+visionOS 1.0+watchOS 8.0+

```
@propertyWrapper @frozen
struct Binding
```

## [主题](/documentation/SwiftUI/AccessibilityFocusState/Binding#topics)

### [获取状态](/documentation/SwiftUI/AccessibilityFocusState/Binding#Getting-the-state)

[当前聚焦的元素。[`var projectedValue: AccessibilityFocusState<Value>.Binding`](/documentation/swiftui/accessibilityfocusstate/binding/projectedvalue)绑定属性引用的底层值。## [See Also](/documentation/SwiftUI/AccessibilityFocusState/Binding#see-also)

### [获取状态](/documentation/SwiftUI/AccessibilityFocusState/Binding#Getting-the-state)

[`var projectedValue: AccessibilityFocusState<Value>.Binding`](/documentation/swiftui/accessibilityfocusstate/projectedvalue)状态值的投影，可用于在视图内容和无障碍焦点位置之间建立绑定。[`var wrappedValue: Value`](/documentation/swiftui/accessibilityfocusstate/wrappedvalue)当前状态值，考虑了由于当前焦点位置而可能生效的任何绑定。

---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityFocusState/Binding
crawled: 2025-12-03T06:49:24Z
---

# AccessibilityFocusState.Binding | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ AccessibilityFocusState ](/documentation/swiftui/accessibilityfocusstate)

- [ AccessibilityFocusState.Binding ](/documentation/SwiftUI/AccessibilityFocusState/Binding)

- [ AccessibilityFocusState ](/documentation/swiftui/accessibilityfocusstate)

-  AccessibilityFocusState.Binding 

Structure# AccessibilityFocusState.Binding

iOS 15.0+iPadOS 15.0+Mac Catalyst 15.0+macOS 12.0+tvOS 15.0+visionOS 1.0+watchOS 8.0+

```
@propertyWrapper @frozen
struct Binding
```

## [Topics](/documentation/SwiftUI/AccessibilityFocusState/Binding#topics)

### [Getting the state](/documentation/SwiftUI/AccessibilityFocusState/Binding#Getting-the-state)

[`var projectedValue: AccessibilityFocusState<Value>.Binding`](/documentation/swiftui/accessibilityfocusstate/binding/projectedvalue)The currently focused element.[`var wrappedValue: Value`](/documentation/swiftui/accessibilityfocusstate/binding/wrappedvalue)The underlying value referenced by the bound property.## [See Also](/documentation/SwiftUI/AccessibilityFocusState/Binding#see-also)

### [Getting the state](/documentation/SwiftUI/AccessibilityFocusState/Binding#Getting-the-state)

[`var projectedValue: AccessibilityFocusState<Value>.Binding`](/documentation/swiftui/accessibilityfocusstate/projectedvalue)A projection of the state value that can be used to establish bindings between view content and accessibility focus placement.[`var wrappedValue: Value`](/documentation/swiftui/accessibilityfocusstate/wrappedvalue)The current state value, taking into account whatever bindings might be in effect due to the current location of focus.