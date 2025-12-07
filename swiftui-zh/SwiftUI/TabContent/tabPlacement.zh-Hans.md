---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/tabPlacement(_:)
抓取时间： 2025-12-01T10:50:54Z
---

# tabPlacement(_:)

**实例方法**

指定选项卡的位置。

## 声明

```swift
nonisolated func tabPlacement(_ placement: TabPlacement) -> some TabContent<Self.TabValue>

```

## 参数

- **placement**：选项卡的位置。

## 讨论

下面的示例显示了一个有三个标签页的[TabView](../TabView.zh-Hans.md)，其中第二个标签页被固定在 iPad 顶部标签栏的后缘。

```swift
TabView {
    Tab("Home", systemImage: "house") {
        MyHomeView()
    }

    Tab("Downloads", systemImage: "square.and.arrow.down.fill") {
        MyDownloadsView()
    }
    .tabPlacement(.pinned)

    Tab("Browse", systemImage: "list.bullet") {
        MyBrowseView()
    }
}
.tabViewStyle(.sidebarAdaptable)
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/tabPlacement(_:)
crawled: 2025-12-01T10:50:54Z
---

# tabPlacement(_:)

**Instance Method**

Specifies the placement of a tab.

## Declaration

```swift
nonisolated func tabPlacement(_ placement: TabPlacement) -> some TabContent<Self.TabValue>

```

## Parameters

- **placement**: The location of the tab.

## Discussion

The following example shows a [TabView](../TabView.zh-Hans.md) with three tabs where the second tab is pinned to the trailing edge of the top tab bar on iPad.

```swift
TabView {
    Tab("Home", systemImage: "house") {
        MyHomeView()
    }

    Tab("Downloads", systemImage: "square.and.arrow.down.fill") {
        MyDownloadsView()
    }
    .tabPlacement(.pinned)

    Tab("Browse", systemImage: "list.bullet") {
        MyBrowseView()
    }
}
.tabViewStyle(.sidebarAdaptable)
```

