--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationBackgroundInteraction(_:)

抓取时间：2025-12-02T17:30:21Z

---

# presentationBackgroundInteraction(_:)

**实例方法**

控制用户是否可以与演示文稿背后的视图进行交互。

## 声明

```swift
nonisolated func presentationBackgroundInteraction(_ interaction: PresentationBackgroundInteraction) -> some View

```

## 参数

- **interaction**：用户如何与演示文稿背后的视图进行交互的规范。

## 说明

在许多平台上，SwiftUI 会自动禁用您展示的面板背后的视图，因此用户在关闭面板之前无法与该视图进行交互。如果您希望启用交互，请使用此修饰符。

以下示例允许用户在工作表处于最小位置时与其背后的视图进行交互，但在其他位置则无法进行交互：

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationDetents(
                    [.height(120), .medium, .large])
                .presentationBackgroundInteraction(
                    .enabled(upThrough: .height(120)))
        }
    }
}
```

## 设置工作表及其背景的样式

- **presentationCornerRadius(_:)**：请求演示文稿具有特定的圆角半径。

- **presentationBackground(_:)**：使用形状样式设置包含工作表的演示文稿背景。

- **presentationBackground(alignment:content:)**：将包含工作表的演示文稿背景设置为自定义视图。

- **PresentationBackgroundInteraction**：演示文稿背后的视图可用的交互类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationBackgroundInteraction(_:)
crawled: 2025-12-02T17:30:21Z
---

# presentationBackgroundInteraction(_:)

**Instance Method**

Controls whether people can interact with the view behind a presentation.

## Declaration

```swift
nonisolated func presentationBackgroundInteraction(_ interaction: PresentationBackgroundInteraction) -> some View

```

## Parameters

- **interaction**: A specification of how people can interact with the view behind a presentation.

## Discussion

On many platforms, SwiftUI automatically disables the view behind a sheet that you present, so that people can’t interact with the backing view until they dismiss the sheet. Use this modifier if you want to enable interaction.

The following example enables people to interact with the view behind the sheet when the sheet is at the smallest detent, but not at the other detents:

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationDetents(
                    [.height(120), .medium, .large])
                .presentationBackgroundInteraction(
                    .enabled(upThrough: .height(120)))
        }
    }
}
```

## Styling a sheet and its background

- **presentationCornerRadius(_:)**: Requests that the presentation have a specific corner radius.
- **presentationBackground(_:)**: Sets the presentation background of the enclosing sheet using a shape style.
- **presentationBackground(alignment:content:)**: Sets the presentation background of the enclosing sheet to a custom view.
- **PresentationBackgroundInteraction**: The kinds of interaction available to views behind a presentation.

