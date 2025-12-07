--- 来源：https://developer.apple.com/documentation/SwiftUI/View/sectionActions(content:)

抓取时间：2025-11-30T21:14:58Z

---

# sectionActions(content:)

**实例方法**

向 section 添加自定义操作。

## 声明

```swift
nonisolated func sectionActions<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## 说明

在 iOS 上，操作会显示在 section 内容之后。在 macOS 上，操作会在用户将鼠标悬停在 section 上时显示。

以下示例向“类别” section 添加一个“添加”按钮。

```swift
List {
    Label("Home", systemImage: "house")
    Label("Alerts", systemImage: "bell")

    Section("Categories") {
        Label("Climate", systemImage: "fan")
        Label("Lights", systemImage: "lightbulb")
    }
    .sectionActions {
        Button("Add Category", systemImage: "plus") { }
    }
}
```

## 配置标签页

- **TabPlacement**：标签页的显示位置。

- **TabContentBuilder**：用于构建支持程序化选择的选项卡视图的选项卡的结果构建器。此构建器要求选项卡视图中的所有选项卡具有相同的选择类型。

- **TabContent**：为选项卡视图中可通过程序选择的选项卡提供内容的类型。

- **AnyTabContent**：擦除选项卡内容的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/sectionActions(content:)
crawled: 2025-11-30T21:14:58Z
---

# sectionActions(content:)

**Instance Method**

Adds custom actions to a section.

## Declaration

```swift
nonisolated func sectionActions<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## Discussion

On iOS, the actions are displayed as items after the content of the section. On macOS, the actions are displayed when a user hovers over the section.

The following example adds an ‘Add’ button to the ‘Categories’ section.

```swift
List {
    Label("Home", systemImage: "house")
    Label("Alerts", systemImage: "bell")

    Section("Categories") {
        Label("Climate", systemImage: "fan")
        Label("Lights", systemImage: "lightbulb")
    }
    .sectionActions {
        Button("Add Category", systemImage: "plus") { }
    }
}
```

## Configuring a tab

- **TabPlacement**: A place that a tab can appear.
- **TabContentBuilder**: A result builder that constructs tabs for a tab view that supports programmatic selection. This builder requires that all tabs in the tab view have the same selection type.
- **TabContent**: A type that provides content for programmatically selectable tabs in a tab view.
- **AnyTabContent**: Type erased tab content.

