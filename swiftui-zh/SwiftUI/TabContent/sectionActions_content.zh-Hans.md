---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/sectionActions(内容：)
抓取时间： 2025-12-01T10:50:52Z
---

# sectionActions(content:)

**实例方法**

为标签页部分添加自定义操作。

## 声明

```swift
nonisolated func sectionActions<Content>(@ViewBuilder content: () -> Content) -> some TabContent<Self.TabValue> where Content : View

```

## 讨论

在 iOS 上，操作显示在该部分的其他选项卡之后。在 macOS 上，当用户将鼠标悬停在该部分上时，就会显示操作。

对单个[Tab](../Tab.zh-Hans.md)应用此修改器没有任何效果。

下面的示例为 "类别 "部分添加了一个 "添加 "按钮。

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
    .sectionActions {
        Button("Add Category", systemImage: "plus") { }
    }
}
.tabViewStyle(.sidebarAdaptable)
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/sectionActions(content:)
crawled: 2025-12-01T10:50:52Z
---

# sectionActions(content:)

**Instance Method**

Adds custom actions to a tab section.

## Declaration

```swift
nonisolated func sectionActions<Content>(@ViewBuilder content: () -> Content) -> some TabContent<Self.TabValue> where Content : View

```

## Discussion

On iOS, the actions are displayed after the other tabs in the section. On macOS, the actions are displayed when a user hovers over the section.

Applying this modifier to a single [Tab](../Tab.zh-Hans.md) has no effect.

The following example adds an ‘Add’ button to the ‘Categories’ section.

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
    .sectionActions {
        Button("Add Category", systemImage: "plus") { }
    }
}
.tabViewStyle(.sidebarAdaptable)
```

