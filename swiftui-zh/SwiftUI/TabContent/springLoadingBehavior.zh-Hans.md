---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/springLoadingBehavior(_:)
抓取时间： 2025-12-01T10:50:52Z
---

# SpringLoadingBehavior(_:)

**实例方法**

设置标签页的弹簧加载行为。

## 声明

```swift
nonisolated func springLoadingBehavior(_ behavior: SpringLoadingBehavior) -> some TabContent<Self.TabValue>

```

## 参数

- **behavior**：是否启用弹簧加载。如果未指定，默认行为是 `.automatic.`

## 讨论

弹簧加载是指视图在拖放交互过程中被激活。在 iOS 上，当在有拖放内容的视图顶部短暂暂停时可能会出现这种情况。在 macOS 上，类似的短暂停顿或在压力感应系统上拖动过程中的 "强制点击 "也会发生这种情况。这对 tvOS 或 watchOS 没有影响。

这通常用于具有导航或展示效果的视图，允许在不暂停拖动交互的情况下显示目的地。例如，一个按钮可以显示可将拖动的项目投放到其中的文件夹列表。

与`disabled(_:)`不同的是，该修改器会覆盖祖先视图设置的值，而不是与之联合。例如，下面的选项卡允许弹簧加载：

```swift
TabView {
    Tab("Favorites", systemImage: "star") {
        MyFavoritesView()
    }
    .springLoadingBehavior(.enabled)

    ...
}
.springLoadingBehavior(.disabled)
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/springLoadingBehavior(_:)
crawled: 2025-12-01T10:50:52Z
---

# springLoadingBehavior(_:)

**Instance Method**

Sets the spring loading behavior for the tab.

## Declaration

```swift
nonisolated func springLoadingBehavior(_ behavior: SpringLoadingBehavior) -> some TabContent<Self.TabValue>

```

## Parameters

- **behavior**: Whether spring loading is enabled or not. If unspecified, the default behavior is `.automatic.`

## Discussion

Spring loading refers to a view being activated during a drag and drop interaction. On iOS this can occur when pausing briefly on top of a view with dragged content. On macOS this can occur with similar brief pauses or on pressure-sensitive systems by “force clicking” during the drag. This has no effect on tvOS or watchOS.

This is commonly used with views that have a navigation or presentation effect, allowing the destination to be revealed without pausing the drag interaction. For example, a button that reveals a list of folders that a dragged item can be dropped onto.

Unlike `disabled(_:)`, this modifier overrides the value set by an ancestor view rather than being unioned with it. For example, the tab below would allow spring loading:

```swift
TabView {
    Tab("Favorites", systemImage: "star") {
        MyFavoritesView()
    }
    .springLoadingBehavior(.enabled)

    ...
}
.springLoadingBehavior(.disabled)
```

