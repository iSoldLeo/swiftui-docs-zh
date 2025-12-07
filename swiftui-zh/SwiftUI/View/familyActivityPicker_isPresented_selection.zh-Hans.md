--- 来源：https://developer.apple.com/documentation/SwiftUI/View/familyActivityPicker(isPresented:selection:)

抓取时间：2025-11-30T21:30:16Z

---

# familyActivityPicker(isPresented:selection:)

**实例方法**

以工作表的形式呈现活动选择器视图。

## 声明

```swift
@MainActor @preconcurrency func familyActivityPicker(isPresented: Binding<Bool>, selection: Binding<FamilyActivitySelection>) -> some View

```

## 参数

- **isPresented**：一个绑定，指示应用是否显示选择器视图。

- **selection**：一个绑定，用于管理用户选择的类别、应用和网站域。

## 说明

使用此视图修饰符来呈现 `FamilyControls/FamilyActivityPicker`。

```swift
struct ExampleView: View {
    @State var selection = FamilyActivitySelection()
    @State var isPresented = false

   var body: some View {
       Button("Present FamilyActivityPicker") { isPresented = true }
       .familyActivityPicker(isPresented: $isPresented,
                             selection: $selection)
       .onChange(of: selection) { newSelection in
           let applications = selection.applications
           let categories = selection.categories
           let webDomains = selection.webDomains
       }
   }
}
```

## 配置家庭共享

- **FamilyActivityPicker**：用户可在视图中指定应用程序、网站域名和类别，而无需向应用程序透露其选择。

- **familyActivityPicker(headerText:footerText:isPresented:selection:)**：以表格形式呈现活动选择器视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/familyActivityPicker(isPresented:selection:)
crawled: 2025-11-30T21:30:16Z
---

# familyActivityPicker(isPresented:selection:)

**Instance Method**

Presents an activity picker view as a sheet.

## Declaration

```swift
@MainActor @preconcurrency func familyActivityPicker(isPresented: Binding<Bool>, selection: Binding<FamilyActivitySelection>) -> some View

```

## Parameters

- **isPresented**: A binding that indicates whether the app presents the picker view.
- **selection**: A binding that manages the user-selected categories, apps, and web domains.

## Discussion

Use this view modifier to present a `FamilyControls/FamilyActivityPicker`.

```swift
struct ExampleView: View {
    @State var selection = FamilyActivitySelection()
    @State var isPresented = false

   var body: some View {
       Button("Present FamilyActivityPicker") { isPresented = true }
       .familyActivityPicker(isPresented: $isPresented,
                             selection: $selection)
       .onChange(of: selection) { newSelection in
           let applications = selection.applications
           let categories = selection.categories
           let webDomains = selection.webDomains
       }
   }
}
```

## Configuring Family Sharing

- **FamilyActivityPicker**: A view in which users specify applications, web domains, and categories without revealing their choices to the app.
- **familyActivityPicker(headerText:footerText:isPresented:selection:)**: Presents an activity picker view as a sheet.

