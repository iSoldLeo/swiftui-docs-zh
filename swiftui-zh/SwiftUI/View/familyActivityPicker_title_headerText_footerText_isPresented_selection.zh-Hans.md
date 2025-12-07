--- 来源：https://developer.apple.com/documentation/SwiftUI/View/familyActivityPicker(title:headerText:footerText:isPresented:selection:)

抓取时间：2025-12-02T17:23:46Z

---

# familyActivityPicker(title:headerText:footerText:isPresented:selection:)

**实例方法**

显示一个活动选择器，用于选择要管理的应用和网站。

## 声明

```swift
@MainActor @preconcurrency func familyActivityPicker(title: String?, headerText: String? = nil, footerText: String? = nil, isPresented: Binding<Bool>, selection: Binding<FamilyActivitySelection>) -> some View

```

## 参数

- **title**：一个可选字符串，用于指定选择器视图的标题。

- **headerText**：一个可选字符串，用于指定选择器视图的标题文本。

- **footerText**：一个可选字符串，用于指定选择器视图底部的文本。

- **isPresented**：一个绑定，指示应用是否显示选择器视图。

- **selection**：一个绑定，用于管理选定的类别、应用和网站域。

## 讨论

使用此视图修饰符可以显示带有自定义标题的 `FamilyControls/FamilyActivityPicker`。

```swift
struct ContentView: View {
    @State private var selection = FamilyActivitySelection()
    @State private var isPresented = false

    var body: some View {
        Button("Select Activities") {
            isPresented = true
        }
        .familyActivityPicker(
            title: "Choose Apps to Limit",
            headerText: "Select apps and websites to manage",
            footerText: "These selections will be used for screen time limits",
            isPresented: $isPresented,
            selection: $selection
        )
        .onChange(of: selection) { newSelection in
            // Handle the selected activities
            print("Selected \(newSelection.applications.count) apps")
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/familyActivityPicker(title:headerText:footerText:isPresented:selection:)
crawled: 2025-12-02T17:23:46Z
---

# familyActivityPicker(title:headerText:footerText:isPresented:selection:)

**Instance Method**

Present an activity picker sheet for selecting apps and websites to manage.

## Declaration

```swift
@MainActor @preconcurrency func familyActivityPicker(title: String?, headerText: String? = nil, footerText: String? = nil, isPresented: Binding<Bool>, selection: Binding<FamilyActivitySelection>) -> some View

```

## Parameters

- **title**: An optional string that provides a title for the picker view.
- **headerText**: An optional string that provides text for the header of the picker view.
- **footerText**: An optional string that provides text for the footer of the picker view.
- **isPresented**: A binding that indicates whether the app presents the picker view.
- **selection**: A binding that manages the selected categories, apps, and web domains.

## Discussion

Use this view modifier to present a `FamilyControls/FamilyActivityPicker` with a custom title.

```swift
struct ContentView: View {
    @State private var selection = FamilyActivitySelection()
    @State private var isPresented = false

    var body: some View {
        Button("Select Activities") {
            isPresented = true
        }
        .familyActivityPicker(
            title: "Choose Apps to Limit",
            headerText: "Select apps and websites to manage",
            footerText: "These selections will be used for screen time limits",
            isPresented: $isPresented,
            selection: $selection
        )
        .onChange(of: selection) { newSelection in
            // Handle the selected activities
            print("Selected \(newSelection.applications.count) apps")
        }
    }
}
```

