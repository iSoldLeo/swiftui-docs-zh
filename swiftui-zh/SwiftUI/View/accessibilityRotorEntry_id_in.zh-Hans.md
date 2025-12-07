--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotorEntry(id:in:)

抓取时间：2025-11-30T21:29:35Z

---

# accessibilityRotorEntry(id:in:)

**实例方法**

定义一个显式标识符，将此视图的辅助功能元素与辅助功能旋转器 (Accessibility Rotor) 中的一个条目关联起来。

## 声明

```swift
nonisolated func accessibilityRotorEntry<ID>(id: ID, in namespace: Namespace.ID) -> some View where ID : Hashable

```

## 参数

- **id**：一个任意的可哈希标识符。初始化 AccessibilityRotorEntry 时，请传递相同的值。

- **namespace**：使用 `@Namespace()` 创建的命名空间。初始化 `AccessibilityRotorEntry` 时，请传递相同的命名空间。

## 讨论

当创建没有命名空间的 AccessibilityRotorEntry 时，SwiftUI 无法自动查找并显示该元素；或者当 Rotor 条目需要与在 ForEach 循环中生成的复杂视图的子元素关联时，可以使用此选项。

## 配置 Rotor

- **accessibilityLinkedGroup(id:in:)**：链接多个辅助功能元素，以便用户能够快速地从一个元素导航到另一个元素，即使这些元素在辅助功能层级结构中彼此并不相邻。

- **accessibilitySortPriority(_:)**：设置此视图的辅助功能元素相对于同一层级其他元素的排序优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotorEntry(id:in:)
crawled: 2025-11-30T21:29:35Z
---

# accessibilityRotorEntry(id:in:)

**Instance Method**

Defines an explicit identifier tying an Accessibility element for this view to an entry in an Accessibility Rotor.

## Declaration

```swift
nonisolated func accessibilityRotorEntry<ID>(id: ID, in namespace: Namespace.ID) -> some View where ID : Hashable

```

## Parameters

- **id**: An arbitrary hashable identifier. Pass this same value when initializing an AccessibilityRotorEntry.
- **namespace**: A namespace created with `@Namespace()`. Pass this same namespace when initializing an `AccessibilityRotorEntry`.

## Discussion

Use this when creating an AccessibilityRotorEntry without a namespace does not allow SwiftUI to automatically find and reveal the element, or when the Rotor entry should be associated with a sub-element of a complex view generated in a ForEach, for example.

## Configuring rotors

- **accessibilityLinkedGroup(id:in:)**: Links multiple accessibility elements so that the user can quickly navigate from one element to another, even when the elements are not near each other in the accessibility hierarchy.
- **accessibilitySortPriority(_:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

