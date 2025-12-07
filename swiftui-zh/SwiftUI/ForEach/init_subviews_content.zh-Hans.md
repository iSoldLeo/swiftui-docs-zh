---
来源：https://developer.apple.com/documentation/SwiftUI/ForEach/init(subviews:content:)
抓取时间： 2025-12-01T00:43:56Z
---

# init(subviews:content:)

**Initializer**

创建一个实例，用于唯一标识视图，并根据给定视图的子视图跨更新创建视图。

### 声明

```swift
init<V>(subviews view: V, @ViewBuilder content: @escaping (Subview) -> Content) where Data == ForEachSubviewCollection<Content>, ID == Subview.ID, Content : View, V : View
```

## 参数

- **view**：要提取子视图的视图。
- **content**：从子视图创建视图的视图生成器。

### 讨论

子视图是它们所代表的已解析视图的代理，这意味着应用于原始视图的修改器将在应用于子视图的修改器之前被应用，而且视图是使用其容器的环境来解析的，**而不是其子视图代理的环境。此外，由于子视图必须代表单个叶视图或容器，因此在应用样式后，子视图可能会代表一个视图。因此，尝试对其应用样式可能没有任何效果。


---
source: https://developer.apple.com/documentation/SwiftUI/ForEach/init(subviews:content:)
crawled: 2025-12-01T00:43:56Z
---

# init(subviews:content:)

**Initializer**

Creates an instance that uniquely identifies and creates views across updates based on the subviews of a given view.

## Declaration

```swift
init<V>(subviews view: V, @ViewBuilder content: @escaping (Subview) -> Content) where Data == ForEachSubviewCollection<Content>, ID == Subview.ID, Content : View, V : View
```

## Parameters

- **view**: The view to extract the subviews of.
- **content**: The view builder that creates views from subviews.

## Discussion

Subviews are proxies to the resolved view they represent, meaning that modifiers applied to the original view will be applied before modifiers applied to the subview, and the view is resolved using the environment of its container, *not* the environment of the its subview proxy. Additionally, because subviews must represent a single leaf view, or container, a subview may represent a view after the application of styles. As such, attempting to apply a style to it may have no effect.

