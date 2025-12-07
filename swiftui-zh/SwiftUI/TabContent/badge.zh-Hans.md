---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/badge(_:)
抓取时间： 2025-12-03T06:01:47Z
---

# badge(_:)

**实例方法**

根据整数值为标签页生成徽章。

## 声明

```swift
nonisolated func badge(_ count: Int) -> some TabContent<Self.TabValue>

```

## 参数

- **count**：要在徽章中显示的整数值。将该值设为零可隐藏徽章。

## 讨论

使用徽章可传递有关视图的可选补充信息。提供的数字将作为数字指示器显示在给定的标签页上。

下面的示例显示了一个[TabView](../TabView.zh-Hans.md)，其值为`alerts.count`，显示为警报选项卡上的徽章。

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }
    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }
    .badge(alerts.count)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/badge(_:)
crawled: 2025-12-03T06:01:47Z
---

# badge(_:)

**Instance Method**

Generates a badge for a tab from an integer value.

## Declaration

```swift
nonisolated func badge(_ count: Int) -> some TabContent<Self.TabValue>

```

## Parameters

- **count**: An integer value to display in the badge. Set the value to zero to hide the badge.

## Discussion

Use a badge to convey optional, supplementary information about a view. The number provided will appear as a numerical indicator on the given tab.

The following example shows a [TabView](../TabView.zh-Hans.md) with the value of `alerts.count` displayed as a badge on the alerts tab.

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }
    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }
    .badge(alerts.count)
}
```

