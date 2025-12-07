--- 来源：https://developer.apple.com/documentation/SwiftUI/View/familyActivityPicker(headerText:footerText:isPresented:selection:)

抓取时间：2025-11-30T21:30:17Z

---

# familyActivityPicker(headerText:footerText:isPresented:selection:)

**实例方法**

以工作表的形式呈现活动选择器视图。

## 声明

```swift
@MainActor @preconcurrency func familyActivityPicker(headerText: String? = nil, footerText: String? = nil, isPresented: Binding<Bool>, selection: Binding<FamilyActivitySelection>) -> some View

```

## 参数

- **headerText**：可选字符串，用于指定选择器视图的标题文本。

- **footerText**：可选字符串，用于指定选择器视图的页脚文本。

- **isPresented**：绑定，指示应用是否显示选择器视图。

- **selection**：用于管理用户选择的类别、应用和网站域的绑定。

## 讨论

使用此视图修饰符显示 `FamilyControls/FamilyActivityPicker`。

## 配置家庭共享

- **FamilyActivityPicker**：用户可在视图中指定应用、网站域和类别，而无需向应用显示其选择。

- **familyActivityPicker(isPresented:selection:)**：以工作表的形式显示活动选择器视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/familyActivityPicker(headerText:footerText:isPresented:selection:)
crawled: 2025-11-30T21:30:17Z
---

# familyActivityPicker(headerText:footerText:isPresented:selection:)

**Instance Method**

Presents an activity picker view as a sheet.

## Declaration

```swift
@MainActor @preconcurrency func familyActivityPicker(headerText: String? = nil, footerText: String? = nil, isPresented: Binding<Bool>, selection: Binding<FamilyActivitySelection>) -> some View

```

## Parameters

- **headerText**: An optional string that provides text for the header of the picker view.
- **footerText**: An optional string that provides text for the footer of the picker view.
- **isPresented**: A binding that indicates whether the app presents the picker view.
- **selection**: A binding that manages the user-selected categories, apps, and web domains.

## Discussion

Use this view modifier to present a `FamilyControls/FamilyActivityPicker`.

## Configuring Family Sharing

- **FamilyActivityPicker**: A view in which users specify applications, web domains, and categories without revealing their choices to the app.
- **familyActivityPicker(isPresented:selection:)**: Presents an activity picker view as a sheet.

