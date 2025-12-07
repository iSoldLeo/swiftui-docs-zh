---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/TabCustomization/tabBarVisibility
抓取时间： 2025-12-03T17:20:58Z
---

# tabBarVisibility

**实例属性**

标签栏中标签的可见性。

## 声明

```swift
var tabBarVisibility: Visibility { get }
```

## 讨论

您可以通过`TabContent/defaultVisibility(_:for)` 和`AdaptableTabBarPlacement.tabBar` 的位置来更改默认可见性。

如果 ID 未与标签页关联或标签页未自定义，则返回`.automatic` 的默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/TabCustomization/tabBarVisibility
crawled: 2025-12-03T17:20:58Z
---

# tabBarVisibility

**Instance Property**

The visibility of the tab in the tab bar.

## Declaration

```swift
var tabBarVisibility: Visibility { get }
```

## Discussion

You can change the default visibility by using the `TabContent/defaultVisibility(_:for)` with a `AdaptableTabBarPlacement.tabBar` placement.

If the ID isn’t associated with a tab or the tab has not been customized, a default value of `.automatic` is returned.

