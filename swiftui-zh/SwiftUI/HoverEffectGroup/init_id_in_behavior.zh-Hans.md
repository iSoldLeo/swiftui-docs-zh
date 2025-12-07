--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectGroup/init(id:in:behavior:)

抓取时间：2025-12-01T11:34:57Z

---

# init(id:in:behavior:)

**Initializer**

创建一个新的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)。

## 声明

```swift
init(id: String?, in namespace: Namespace.ID, behavior: HoverEffectGroup.Behavior = .activatesGroup)
```

## 参数

- **id**：用于为组指定的可选 ID。如果提供，组将通过 ID 和命名空间的组合进行唯一标识。

- **namespace**：用于标识组的命名空间。

- **behavior**：效果相对于组中其他效果的行为方式。 ## 返回值

一个新的悬停效果组


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectGroup/init(id:in:behavior:)
crawled: 2025-12-01T11:34:57Z
---

# init(id:in:behavior:)

**Initializer**

Creates a new [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md).

## Declaration

```swift
init(id: String?, in namespace: Namespace.ID, behavior: HoverEffectGroup.Behavior = .activatesGroup)
```

## Parameters

- **id**: An optional id to give the group. If provided, the group will be uniquely identified by combining the id and the namespace.
- **namespace**: The namespace that identifies the group.
- **behavior**: How the effect will behave relative to other effects in the group.

## Return Value

A new HoverEffectGroup

