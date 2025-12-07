--- 来源：https://developer.apple.com/documentation/SwiftUI/DefaultFocusEvaluationPriority
抓取时间：2025-12-02T17:43:17Z

---

# DefaultFocusEvaluationPriority

**Structure**

在不同情况下评估焦点移动位置时，默认焦点偏好的优先级设置。

## 声明

```swift
struct DefaultFocusEvaluationPriority
```

## 获取优先级

- **automatic**：当焦点自动移动到受影响的分支时，使用默认焦点偏好；但如果焦点移动是由用户发起的导航命令驱动的，则忽略该偏好。

- **userInitiated**：当焦点移动到受影响的分支时，始终使用默认焦点偏好。

## 控制默认焦点

- **prefersDefaultFocus(_:in:)**：指示给定命名空间下的视图应默认获得焦点。

- **defaultFocus(_:_:priority:)**：定义窗口中用于评估默认焦点的区域，方法是为给定的焦点状态绑定赋值。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/DefaultFocusEvaluationPriority
crawled: 2025-12-02T17:43:17Z
---

# DefaultFocusEvaluationPriority

**Structure**

Prioritizations for default focus preferences when evaluating where to move focus in different circumstances.

## Declaration

```swift
struct DefaultFocusEvaluationPriority
```

## Getting the priorities

- **automatic**: Use the default focus preference when focus moves into the affected branch automatically, but ignore it when the movement is driven by a user-initiated navigation command.
- **userInitiated**: Always use the default focus preference when focus moves into the affected branch.

## Controlling default focus

- **prefersDefaultFocus(_:in:)**: Indicates that the view should receive focus by default for a given namespace.
- **defaultFocus(_:_:priority:)**: Defines a region of the window in which default focus is evaluated by assigning a value to a given focus state binding.

## Conforms To

- Sendable
- SendableMetatype

