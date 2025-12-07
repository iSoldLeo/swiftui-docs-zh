--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollInputBehavior
抓取时间：2025-12-02T17:40:49Z

---

# ScrollInputBehavior

**Structure**

定义输入框是否应该滚动视图的类型。

## 声明

```swift
struct ScrollInputBehavior
```

## 类型属性

- **automatic**：指示系统是否应该判断关联的输入框是否应该滚动视图。

- **disabled**：指示关联的输入框不应该滚动视图。

- **enabled**：指示关联的输入框应该滚动视图。

## 管理不同输入框的滚动

- **scrollInputBehavior(_:for:)**：启用或禁用使用特定输入框时可滚动视图的滚动功能。

- **ScrollInputKind**：用于滚动视图的输入框。

## 符合以下规范

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollInputBehavior
crawled: 2025-12-02T17:40:49Z
---

# ScrollInputBehavior

**Structure**

A type that defines whether input should scroll a view.

## Declaration

```swift
struct ScrollInputBehavior
```

## Type Properties

- **automatic**: Indicates that the system should determine whether the associated input scrolls a view.
- **disabled**: Indicates that the associated input should not scroll a view.
- **enabled**: Indicates that the associated input should scroll a view.

## Managing scrolling for different inputs

- **scrollInputBehavior(_:for:)**: Enables or disables scrolling in scrollable views when using particular inputs.
- **ScrollInputKind**: Inputs used to scroll views.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

