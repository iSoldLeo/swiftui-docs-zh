---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/subscript(sidebarVisibility:)
抓取时间：2025-12-02T21:00:03Z
---

# subscript(sidebarVisibility:)

**实例下标**

自定义标识符标识的选项卡的可见性。

## 声明

```swift
subscript(sidebarVisibility id: String) -> Visibility { get set }
```

## 概览

可通过标签页 id 的下标强制设置可见性：

```swift
customization[sidebarVisibility: "com.myApp.alerts"] = .hidden
```

您可以通过[defaultVisibility(_:for:)](../TabContent/defaultVisibility___for.zh-Hans.md) 和[sidebar](../AdaptableTabBarPlacement/sidebar.zh-Hans.md) 的位置来更改默认可见性。

```swift
Tab("Alerts", systemImage: "bell", value: .alerts) {
    AlertsView()
}
.customizationID("com.myApp.alerts")
.defaultVisibility(.hidden, for: .sidebar)
```

如果 ID 未与标签页关联或标签页未自定义，则返回`.automatic` 的默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/subscript(sidebarVisibility:)
crawled: 2025-12-02T21:00:03Z
---

# subscript(sidebarVisibility:)

**Instance Subscript**

The visibility of the tab identified by its customization identifier.

## Declaration

```swift
subscript(sidebarVisibility id: String) -> Visibility { get set }
```

## Overview

Visibility can be set imperatively by subscripting with the tab’s id:

```swift
customization[sidebarVisibility: "com.myApp.alerts"] = .hidden
```

You can change the default visibility by using the [defaultVisibility(_:for:)](../TabContent/defaultVisibility___for.zh-Hans.md) with a [sidebar](../AdaptableTabBarPlacement/sidebar.zh-Hans.md) placement.

```swift
Tab("Alerts", systemImage: "bell", value: .alerts) {
    AlertsView()
}
.customizationID("com.myApp.alerts")
.defaultVisibility(.hidden, for: .sidebar)
```

If the ID isn’t associated with a tab or the tab has not been customized, a default value of `.automatic` is returned.

