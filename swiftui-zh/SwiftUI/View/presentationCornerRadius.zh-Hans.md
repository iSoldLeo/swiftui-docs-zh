--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationCornerRadius(_:)

抓取时间：2025-12-02T17:30:19Z

---

# presentationCornerRadius(_:)

**实例方法**

请求演示文稿具有指定的圆角半径。

## 声明

```swift
nonisolated func presentationCornerRadius(_ cornerRadius: CGFloat?) -> some View

```

## 参数

- **cornerRadius**：圆角半径，或 `nil` 使用系统默认值。

## 说明

使用此修饰符更改演示文稿的圆角半径。

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationDetents([.medium, .large])
                .presentationCornerRadius(21)
        }
    }
}
```

## 设置工作表及其背景的样式

- **presentationBackground(_:)**：使用形状样式设置包含演示文稿的工作表的背景。

- **presentationBackground(alignment:content:)**：将包含该表的演示文稿背景设置为自定义视图。

- **presentationBackgroundInteraction(_:)**：控制用户是否可以与演示文稿背后的视图进行交互。

- **PresentationBackgroundInteraction**：演示文稿背后的视图可用的交互类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationCornerRadius(_:)
crawled: 2025-12-02T17:30:19Z
---

# presentationCornerRadius(_:)

**Instance Method**

Requests that the presentation have a specific corner radius.

## Declaration

```swift
nonisolated func presentationCornerRadius(_ cornerRadius: CGFloat?) -> some View

```

## Parameters

- **cornerRadius**: The corner radius, or `nil` to use the system default.

## Discussion

Use this modifier to change the corner radius of a presentation.

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationDetents([.medium, .large])
                .presentationCornerRadius(21)
        }
    }
}
```



## Styling a sheet and its background

- **presentationBackground(_:)**: Sets the presentation background of the enclosing sheet using a shape style.
- **presentationBackground(alignment:content:)**: Sets the presentation background of the enclosing sheet to a custom view.
- **presentationBackgroundInteraction(_:)**: Controls whether people can interact with the view behind a presentation.
- **PresentationBackgroundInteraction**: The kinds of interaction available to views behind a presentation.

