---
来源： https://developer.apple.com/documentation/swiftui/accessibilityactionkind
抓取时间： 2025-12-04T13:39:42Z
---

# 无障碍操作类型

**Structure**

定义可用无障碍操作类型的结构。

## 声明

```swift
struct AccessibilityActionKind
```

## 获取动作类型

- **default**：表示默认无障碍操作的值。
- **delete**：表示默认无障碍操作的值。
- **escape**：表示解除模式视图或取消操作的无障碍操作的值。
- **magicTap**：表示解除模态视图或取消操作的无障碍操作的值。
- **showMenu**：表示解除模态视图或取消操作的无障碍操作的值。

## 创建操作类型

- **init(named:)**

## 为视图添加操作

- **accessibilityAction(_:_:)**：为视图添加辅助操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图进行交互。
- **accessibilityActions(_:)**：为视图添加多个无障碍操作。
- **accessibilityAction(named:_:)**：为视图添加一个辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互。
- **accessibilityAction(action:label:)**：为视图添加辅助操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互。
- **accessibilityAction(intent:label:)**：将`label` 内容标记的无障碍操作添加到视图中。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互。执行操作时，`intent` 将被调用。
- **accessibilityAction(_:intent:)**：将代表`actionKind` 的无障碍操作添加到视图中。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互。执行操作时，将调用`intent`。
- **accessibilityAction(named:intent:)**：向视图添加标有`name`的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互。执行操作时，`intent` 将被调用。
- **accessibilityAdjustableAction(_:)**：为视图添加可调整的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图进行交互。
- **accessibilityScrollAction(_:)**：为视图添加无障碍滚动操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互。
- **accessibilityActions(category:_:)**：为视图添加多个具有特定类别的辅助操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互，并按类别分组。当视图中应用了多个类别相同的操作修改器时，这些操作会合并在一起。
- **AccessibilityAdjustmentDirection**：在进行无障碍调整时使用的方向指示器。
- **AccessibilityActionCategory**：指定由系统提供和命名的无障碍操作类别。

## 符合

- 可等同
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/swiftui/accessibilityactionkind
crawled: 2025-12-04T13:39:42Z
---

# AccessibilityActionKind

**Structure**

The structure that defines the kinds of available accessibility actions.

## Declaration

```swift
struct AccessibilityActionKind
```

## Getting the kind of action

- **default**: The value that represents the default accessibility action.
- **delete**
- **escape**: The value that represents an accessibility action that dismisses a modal view or cancels an operation.
- **magicTap**
- **showMenu**

## Creating an action type

- **init(named:)**

## Adding actions to views

- **accessibilityAction(_:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityActions(_:)**: Adds multiple accessibility actions to the view.
- **accessibilityAction(named:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(action:label:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(intent:label:)**: Adds an accessibility action labeled by the contents of `label` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(_:intent:)**: Adds an accessibility action representing `actionKind` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(named:intent:)**: Adds an accessibility action labeled `name` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAdjustableAction(_:)**: Adds an accessibility adjustable action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityScrollAction(_:)**: Adds an accessibility scroll action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityActions(category:_:)**: Adds multiple accessibility actions to the view with a specific category. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action and are grouped by their category. When multiple action modifiers with an equal category are applied to the view, the actions are combined together.
- **AccessibilityAdjustmentDirection**: A directional indicator you use when making an accessibility adjustment.
- **AccessibilityActionCategory**: Designates an accessibility action category that is provided and named by the system.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

