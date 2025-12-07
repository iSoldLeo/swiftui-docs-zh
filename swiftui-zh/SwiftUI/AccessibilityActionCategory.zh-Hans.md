--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityActionCategory

抓取时间：2025-12-02T17:43:55Z

---

# AccessibilityActionCategory

**Structure**

指定一个由系统提供并命名的辅助功能操作类别。

## 声明

```swift
struct AccessibilityActionCategory
```

## 初始化器

- **init(_:)**：创建一个由 `name` 标记的自定义操作类别。

## 类型属性

- **default**：视图默认操作的辅助功能操作类别。此类别会替换系统提供的用于 VoiceOver 等辅助功能技术的操作转子。

- **edit**：用于关联与文本编辑相关的操作的辅助功能操作类别。此类别取代了系统提供的用于 VoiceOver 等辅助功能的编辑操作。

## 向视图添加操作

- **accessibilityAction(_:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityActions(_:)**：向视图添加多个辅助功能操作。

- **accessibilityAction(named:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(action:label:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(intent:label:)**：向视图添加一个由 `label` 内容标记的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityAction(_:intent:)**：向视图添加一个代表 `actionKind` 的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityAction(named:intent:)**：向视图添加一个标记为 `name` 的辅助功能操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。执行操作时，将调用 `intent`。

- **accessibilityAdjustableAction(_:)**：向视图添加一个辅助功能可调节操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。

- **accessibilityScrollAction(_:)**：向视图添加一个辅助功能滚动操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。

- **accessibilityActions(category:_:)**：向视图添加多个具有特定类别的辅助功能操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互，并按类别分组。当多个具有相同类别的操作修饰符应用于视图时，这些操作将合并在一起。

- **AccessibilityActionKind**：定义可用辅助功能操作类型的结构。

- **AccessibilityAdjustmentDirection**：进行辅助功能调整时使用的方向指示符。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityActionCategory
crawled: 2025-12-02T17:43:55Z
---

# AccessibilityActionCategory

**Structure**

Designates an accessibility action category that is provided and named by the system.

## Declaration

```swift
struct AccessibilityActionCategory
```

## Initializers

- **init(_:)**: Creates a custom action category labeled by `name`.

## Type Properties

- **default**: An accessibility action category for the default actions of a view. This category replaces the system provided actions rotor for accessibility technologies like VoiceOver.
- **edit**: An accessibility action category for associating actions related to editing text. This category replaces the system provided Edit actions for accessibility technologies like VoiceOver.

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
- **AccessibilityActionKind**: The structure that defines the kinds of available accessibility actions.
- **AccessibilityAdjustmentDirection**: A directional indicator you use when making an accessibility adjustment.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

