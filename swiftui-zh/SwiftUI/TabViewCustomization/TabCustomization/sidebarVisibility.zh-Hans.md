---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/TabCustomization/sidebarVisibility
抓取时间： 2025-12-03T17:20:57Z
---

# 侧边栏可见性

**实例属性**

侧边栏中选项卡的可见性。

## 声明

```swift
var sidebarVisibility: Visibility { get set }
```

## 讨论

可以通过标签页 id 的下标来强制设置可见性：

```swift
customization[tab: "com.myApp.alerts"].sidebarVisibility = .hidden
```

您可以通过`TabContent/defaultVisibility(_:for)` 和`AdaptableTabBarPlacement.sidebar` 的位置来更改默认可见性。

```swift
Tab("Alerts", systemImage: "bell", value: .alerts) {
    AlertsView()
}
.customizationID("com.myApp.alerts")
.defaultVisibility(.hidden, for: .sidebar)
```

如果 ID 未与标签页关联或标签页未自定义，则返回`.automatic` 的默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/TabCustomization/sidebarVisibility
crawled: 2025-12-03T17:20:57Z
---

# sidebarVisibility

**Instance Property**

The visibility of the tab in the sidebar.

## Declaration

```swift
var sidebarVisibility: Visibility { get set }
```

## Discussion

Visibility can be set imperatively by subscripting with the tab’s id:

```swift
customization[tab: "com.myApp.alerts"].sidebarVisibility = .hidden
```

You can change the default visibility by using `TabContent/defaultVisibility(_:for)` with a `AdaptableTabBarPlacement.sidebar` placement.

```swift
Tab("Alerts", systemImage: "bell", value: .alerts) {
    AlertsView()
}
.customizationID("com.myApp.alerts")
.defaultVisibility(.hidden, for: .sidebar)
```

If the ID isn’t associated with a tab or the tab has not been customized, a default value of `.automatic` is returned.

