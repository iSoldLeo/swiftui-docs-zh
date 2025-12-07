--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityLinkedGroup(id:in:)

抓取时间：2025-12-02T17:44:38Z

---

# accessibilityLinkedGroup(id:in:)

**实例方法**

链接多个辅助功能元素，使用户能够快速地从一个元素导航到另一个元素，即使这些元素在辅助功能层级结构中彼此并不相邻。

## 声明

```swift
nonisolated func accessibilityLinkedGroup<ID>(id: ID, in namespace: Namespace.ID) -> some View where ID : Hashable

```

## 参数

- **id**：用于分隔同一命名空间内链接元素集的哈希标识符。具有匹配的 `namespace` 和 `id` 的元素将被链接在一起。

- **namespace**：用于组织链接的辅助功能元素的命名空间。在此命名空间中，所有标记为 `accessibilityLink` 且具有指定 `id` 的元素将被链接在一起。

## 讨论

例如，此功能可用于在列表内容和相同内容的详细视图之间快速跳转。所有标记为 `accessibilityLinkedGroup` 且具有相同命名空间和标识符的元素将被链接在一起。

## 配置转子

- **accessibilityRotorEntry(id:in:)**：定义一个显式标识符，将此视图的辅助功能元素与辅助功能转子中的条目关联起来。

- **accessibilitySortPriority(_:)**：设置此视图的辅助功能元素相对于同一级别其他元素的排序优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityLinkedGroup(id:in:)
crawled: 2025-12-02T17:44:38Z
---

# accessibilityLinkedGroup(id:in:)

**Instance Method**

Links multiple accessibility elements so that the user can quickly navigate from one element to another, even when the elements are not near each other in the accessibility hierarchy.

## Declaration

```swift
nonisolated func accessibilityLinkedGroup<ID>(id: ID, in namespace: Namespace.ID) -> some View where ID : Hashable

```

## Parameters

- **id**: A hashable identifier used to separate sets of linked elements within the same namespace. Elements with matching `namespace` and `id` will be linked together.
- **namespace**: The namespace to use to organize linked accessibility elements. All elements marked with `accessibilityLink` in this namespace and with the specified `id` will be linked together.

## Discussion

This can be useful to allow quickly jumping between content in a list and the same content shown in a detail view, for example. All elements marked with `accessibilityLinkedGroup` with the same namespace and identifier will be linked together.

## Configuring rotors

- **accessibilityRotorEntry(id:in:)**: Defines an explicit identifier tying an Accessibility element for this view to an entry in an Accessibility Rotor.
- **accessibilitySortPriority(_:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

