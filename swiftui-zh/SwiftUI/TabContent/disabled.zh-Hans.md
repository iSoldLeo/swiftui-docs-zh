---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/disabled(_:)
抓取时间： 2025-12-01T10:50:47Z
---

# disabled(_:)

**实例方法**

控制用户是否可以与此选项卡交互。

## 声明

```swift
nonisolated func disabled(_ disabled: Bool) -> some TabContent<Self.TabValue>

```

## 参数

- **disabled**：布尔值，用于确定用户是否可以与此选项卡交互。

## 讨论

下面的示例显示[TabView](../TabView.zh-Hans.md) 有一个不可选择的选项卡。

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }
    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }
    .disabled(alertsDisabled)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/disabled(_:)
crawled: 2025-12-01T10:50:47Z
---

# disabled(_:)

**Instance Method**

Controls whether users can interact with this tab.

## Declaration

```swift
nonisolated func disabled(_ disabled: Bool) -> some TabContent<Self.TabValue>

```

## Parameters

- **disabled**: A Boolean value that determines whether users can interact with this tab.

## Discussion

The following example shows a [TabView](../TabView.zh-Hans.md) with one tab that is not selectable.

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }
    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }
    .disabled(alertsDisabled)
}
```

