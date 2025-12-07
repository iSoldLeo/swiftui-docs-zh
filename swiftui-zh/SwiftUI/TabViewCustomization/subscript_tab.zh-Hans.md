---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/subscript(tab:)
抓取时间：2025-12-02T21:00:04Z
---

# subscript(tab:)

**实例下标**

标签页的自定义标识符。

## 声明

```swift
subscript(tab id: String) -> TabViewCustomization.TabCustomization { get set }
```

## 概览

通过使用标签页 ID 作为下标，可以强制设置属性。下面的示例设置了选项卡侧边栏的可见性：

```swift
customization[tab: "com.myApp.alerts"].sidebarVisibility = .hidden
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/subscript(tab:)
crawled: 2025-12-02T21:00:04Z
---

# subscript(tab:)

**Instance Subscript**

The customization of the tab, identified by its customization identifier.

## Declaration

```swift
subscript(tab id: String) -> TabViewCustomization.TabCustomization { get set }
```

## Overview

You can imperatively set properties by subscripting with the tab ID. The following example sets the tab’s sidebar visibility:

```swift
customization[tab: "com.myApp.alerts"].sidebarVisibility = .hidden
```

