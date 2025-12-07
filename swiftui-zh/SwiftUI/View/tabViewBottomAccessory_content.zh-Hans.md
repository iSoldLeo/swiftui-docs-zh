---

来源：https://developer.apple.com/documentation/SwiftUI/View/tabViewBottomAccessory(content:)

抓取时间：2025-11-30T21:11:06Z

---

# tabViewBottomAccessory(content:)

**实例方法**

将一个视图设置为标签页的底部附件。

## 声明

```swift
nonisolated func tabViewBottomAccessory<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## 说明

在 iPhone 上，底部附件的位置取决于标签栏的大小：当标签栏处于正常大小时，附件会显示在标签栏上方；当标签栏折叠时，附件会内嵌显示。使用 [tabViewBottomAccessoryPlacement](../EnvironmentValues/tabViewBottomAccessoryPlacement.zh-Hans.md) 环境变量可以根据附件的位置调整其内容。

以下示例将一个状态视图设置为 `TabView` 底部附件。

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }

    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }

    TabSection("Categories") {
        Tab("Climate", systemImage: "fan") {
            ClimateView()
        }

        Tab("Lights", systemImage: "lightbulb") {
            LightsView()
        }
    }
}
.tabViewBottomAccessory {
    HomeStatusView()
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/tabViewBottomAccessory(content:)
crawled: 2025-11-30T21:11:06Z
---

# tabViewBottomAccessory(content:)

**Instance Method**

Places a view as the bottom accessory of the tab view.

## Declaration

```swift
nonisolated func tabViewBottomAccessory<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## Discussion

On iPhone, the placement of the bottom accessory depends on the tab bar size: when the tab bar is normal size, the accessory appears above it; when the tab bar is collapsed, the accessory displays inline. Use the [tabViewBottomAccessoryPlacement](../EnvironmentValues/tabViewBottomAccessoryPlacement.zh-Hans.md) environment value to adjust the accessory’s content based on its placement.

The following example sets a status view as the `TabView` bottom accessory.

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }

    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }

    TabSection("Categories") {
        Tab("Climate", systemImage: "fan") {
            ClimateView()
        }

        Tab("Lights", systemImage: "lightbulb") {
            LightsView()
        }
    }
}
.tabViewBottomAccessory {
    HomeStatusView()
}
```

