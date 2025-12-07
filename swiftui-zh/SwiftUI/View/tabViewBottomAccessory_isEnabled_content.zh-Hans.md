--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tabViewBottomAccessory(isEnabled:content:)

抓取时间：2025-12-02T17:26:01Z

---

# tabViewBottomAccessory(isEnabled:content:)

**实例方法**

将一个视图放置为标签页底部的辅助视图。使用此修饰符可以动态显示和隐藏辅助视图。

## 声明

```swift
nonisolated func tabViewBottomAccessory<Content>(isEnabled: Bool, @ViewBuilder content: () -> Content) -> some View where Content : View

```

## 参数

- **isEnabled**：如果为 true，则显示底部辅助视图；否则，隐藏底部辅助视图。

- **content**：标签页辅助视图的内容视图。

## 说明

在 iPhone 上，底部辅助视图的位置取决于标签栏的大小：当标签栏为正常大小时，辅助视图会出现在其上方；当标签栏折叠时，该附件会以内嵌方式显示。使用 [tabViewBottomAccessoryPlacement](../EnvironmentValues/tabViewBottomAccessoryPlacement.zh-Hans.md) 环境变量可以根据附件的位置调整其内容。

以下示例显示了状态更新时，`TabView` 底部附件中的状态视图。

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
.tabViewBottomAccessory(isEnabled: hasStatusUpdate) {
    HomeStatusView()
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/tabViewBottomAccessory(isEnabled:content:)
crawled: 2025-12-02T17:26:01Z
---

# tabViewBottomAccessory(isEnabled:content:)

**Instance Method**

Places a view as the bottom accessory of the tab view. Use this modifier to dynamically show and hide the accessory view.

## Declaration

```swift
nonisolated func tabViewBottomAccessory<Content>(isEnabled: Bool, @ViewBuilder content: () -> Content) -> some View where Content : View

```

## Parameters

- **isEnabled**: If true, the bottom accessory is shown; otherwise, the bottom accessory is hidden.
- **content**: The content view of the tab view accessory.

## Discussion

On iPhone, the placement of the bottom accessory depends on the tab bar size: when the tab bar is normal size, the accessory appears above it; when the tab bar is collapsed, the accessory displays inline. Use the [tabViewBottomAccessoryPlacement](../EnvironmentValues/tabViewBottomAccessoryPlacement.zh-Hans.md) environment value to adjust the accessory’s content based on its placement.

The following example shows a status view in the `TabView` bottom accessory when there’s a status update.

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
.tabViewBottomAccessory(isEnabled: hasStatusUpdate) {
    HomeStatusView()
}
```

