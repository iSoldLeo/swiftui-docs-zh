--- 来源：https://developer.apple.com/documentation/SwiftUI/View/ignoresSafeArea(_:edges:)

抓取时间：2025-12-02T17:38:56Z

---

# ignoresSafeArea(_:edges:)

**实例方法**

扩展视图的安全区域。

## 声明

```swift
nonisolated func ignoresSafeArea(_ regions: SafeAreaRegions = .all, edges: Edge.Set = .all) -> some View

```

## 参数

- **regions**：要扩展视图安全区域的区域。默认情况下，此修饰符会扩展到所有安全区域类型。

- **edges**：要扩展的边集。未包含在此集合中的任何边将保持不变。默认情况下，此集合包含所有边。

## 返回值

一个扩展了安全区域的视图。

## 讨论

默认情况下，SwiftUI 布局系统会调整视图的大小和位置，以避开某些安全区域。这确保了系统内容（例如软件键盘或设备边缘）不会遮挡您的视图。要将您的内容扩展到这些区域，您可以使用此修饰符忽略特定边缘上的安全区域。

有关如何使用此修饰符的示例，请参阅 [Adding-a-Background-to-Your-View](../Adding-a-Background-to-Your-View.zh-Hans.md)。

## 保持在安全区域内

- **safeAreaInset(edge:alignment:spacing:content:)**：在修改后的视图旁边显示指定内容。

- **safeAreaPadding(_:)**：将提供的内边距添加到此视图的安全区域。

- **safeAreaPadding(_:_:)**：将提供的内边距添加到此视图的安全区域。

- **SafeAreaRegions**：一组符号安全区域。


---
source: https://developer.apple.com/documentation/SwiftUI/View/ignoresSafeArea(_:edges:)
crawled: 2025-12-02T17:38:56Z
---

# ignoresSafeArea(_:edges:)

**Instance Method**

Expands the safe area of a view.

## Declaration

```swift
nonisolated func ignoresSafeArea(_ regions: SafeAreaRegions = .all, edges: Edge.Set = .all) -> some View

```

## Parameters

- **regions**: The regions to expand the view’s safe area into. The modifier expands into all safe area region types by default.
- **edges**: The set of edges to expand. Any edges that you don’t include in this set remain unchanged. The set includes all edges by default.

## Return Value

A view with an expanded safe area.

## Discussion

By default, the SwiftUI layout system sizes and positions views to avoid certain safe areas. This ensures that system content like the software keyboard or edges of the device don’t obstruct your views. To extend your content into these regions, you can ignore safe areas on specific edges by applying this modifier.

For examples of how to use this modifier, see [Adding-a-Background-to-Your-View](../Adding-a-Background-to-Your-View.zh-Hans.md).

## Staying in the safe areas

- **safeAreaInset(edge:alignment:spacing:content:)**: Shows the specified content beside the modified view.
- **safeAreaPadding(_:)**: Adds the provided insets into the safe area of this view.
- **safeAreaPadding(_:_:)**: Adds the provided insets into the safe area of this view.
- **SafeAreaRegions**: A set of symbolic safe area regions.

