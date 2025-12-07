--- 来源：https://developer.apple.com/documentation/swiftui/accessibilityfocusstate

抓取时间：2025-12-04T13:40:20Z

---

# AccessibilityFocusState

**Structure**

这是一个属性包装器类型，可以读取和写入一个值，该值会在任何激活的辅助功能技术（例如 VoiceOver）的焦点发生变化时由 SwiftUI 更新。

## 声明

```swift
@propertyWrapper @frozen struct AccessibilityFocusState<Value> where Value : Hashable
```

## 概述

使用此功能可以请求 VoiceOver 或其他辅助功能技术以编程方式聚焦到特定元素，或者确定 VoiceOver 或其他辅助功能技术是否聚焦到特定元素。将 [accessibilityFocused(_:equals:)](View/accessibilityFocused___equals.zh-Hans.md) 或 [accessibilityFocused(_:)](View/accessibilityFocused.zh-Hans.md) 与此属性包装器结合使用，可以标识要获取或设置辅助功能焦点的辅助功能元素。当辅助功能焦点进入已修改的辅助功能元素时，框架会更新该属性的包装值，使其与给定的原型值匹配。当辅助功能焦点离开时，SwiftUI 会将可选属性的包装值重置为 `nil`，或将布尔属性的包装值重置为 `false`。以编程方式设置属性值会产生相反的效果，使辅助功能焦点移动到与更新后的值关联的辅助功能元素。

在以下示例中，当 `notification` 发生变化，且其 `isPriority` 属性值为 `true` 时，辅助功能焦点会移动到视图其余内容上方的通知元素 `Text`：

```swift
struct CustomNotification: Equatable {
    var text: String
    var isPriority: Bool
}

struct ContentView: View {
    @Binding var notification: CustomNotification?
    @AccessibilityFocusState var isNotificationFocused: Bool

    var body: some View {
        VStack {
            if let notification = self.notification {
                Text(notification.text)
                    .accessibilityFocused($isNotificationFocused)
            }
            Text("The main content for this view.")
        }
        .onChange(of: notification) { notification in
            if (notification?.isPriority == true)  {
                isNotificationFocused = true
            }
        }

    }
}
```

为了应对辅助功能焦点完全不在辅助功能元素树中，或者辅助功能技术未激活的情况，包装后的值必须是可选的或布尔值。

`AccessibilityFocusState` 的某些初始化器也允许指定辅助功能技术，从而确定此绑定适用于哪些类型的辅助功能焦点。如果您未指定任何辅助功能技术，SwiftUI 将使用所有已激活的辅助功能技术的聚合。

## 创建焦点状态

- **init()**：为布尔值创建一个新的辅助功能焦点状态。

- **init(for:)**：使用您指定的辅助功能技术，为布尔值创建新的辅助功能焦点状态。

## 获取状态

- **projectedValue**：状态值的投影，可用于在视图内容和辅助功能焦点位置之间建立绑定。

- **wrappedValue**：当前状态值，考虑了由于当前焦点位置而生效的任何绑定。

- **AccessibilityFocusState.Binding**

## 控制焦点

- **accessibilityFocused(_:)**：通过将辅助功能元素的焦点状态绑定到给定的布尔状态值来修改此视图。

- **accessibilityFocused(_:equals:)**：通过将辅助功能元素的焦点状态绑定到给定的状态值来修改此视图。

## 符合以下规范

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/accessibilityfocusstate
crawled: 2025-12-04T13:40:20Z
---

# AccessibilityFocusState

**Structure**

A property wrapper type that can read and write a value that SwiftUI updates as the focus of any active accessibility technology, such as VoiceOver, changes.

## Declaration

```swift
@propertyWrapper @frozen struct AccessibilityFocusState<Value> where Value : Hashable
```

## Overview

Use this capability to request that VoiceOver or other accessibility technologies programmatically focus on a specific element, or to determine whether VoiceOver or other accessibility technologies are focused on particular elements. Use [accessibilityFocused(_:equals:)](View/accessibilityFocused___equals.zh-Hans.md) or [accessibilityFocused(_:)](View/accessibilityFocused.zh-Hans.md) in conjunction with this property wrapper to identify accessibility elements for which you want to get or set accessibility focus. When accessibility focus enters the modified accessibility element, the framework updates the wrapped value of this property to match a given prototype value. When accessibility focus leaves, SwiftUI resets the wrapped value of an optional property to `nil` or the wrapped value of a Boolean property to `false`. Setting the property’s value programmatically has the reverse effect, causing accessibility focus to move to whichever accessibility element is associated with the updated value.

In the example below, when `notification` changes, and its  `isPriority` property is `true`, the accessibility focus moves to the notification `Text` element above the rest of the view’s content:

```swift
struct CustomNotification: Equatable {
    var text: String
    var isPriority: Bool
}

struct ContentView: View {
    @Binding var notification: CustomNotification?
    @AccessibilityFocusState var isNotificationFocused: Bool

    var body: some View {
        VStack {
            if let notification = self.notification {
                Text(notification.text)
                    .accessibilityFocused($isNotificationFocused)
            }
            Text("The main content for this view.")
        }
        .onChange(of: notification) { notification in
            if (notification?.isPriority == true)  {
                isNotificationFocused = true
            }
        }

    }
}
```

To allow for cases where accessibility focus is completely absent from the tree of accessibility elements, or accessibility technologies are not active, the wrapped value must be either optional or Boolean.

Some initializers of `AccessibilityFocusState` also allow specifying accessibility technologies, determining to which types of accessibility focus this binding applies. If you specify no accessibility technologies, SwiftUI uses an aggregate of any and all active accessibility technologies.

## Creating a focus state

- **init()**: Creates a new accessibility focus state for a Boolean value.
- **init(for:)**: Creates a new accessibility focus state for a Boolean value, using the accessibility technologies you specify.

## Getting the state

- **projectedValue**: A projection of the state value that can be used to establish bindings between view content and accessibility focus placement.
- **wrappedValue**: The current state value, taking into account whatever bindings might be in effect due to the current location of focus.
- **AccessibilityFocusState.Binding**

## Controlling focus

- **accessibilityFocused(_:)**: Modifies this view by binding its accessibility element’s focus state to the given boolean state value.
- **accessibilityFocused(_:equals:)**: Modifies this view by binding its accessibility element’s focus state to the given state value.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

