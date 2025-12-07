--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationBackground(_:)

抓取时间：2025-12-02T17:30:20Z

---

# presentationBackground(_:)

**实例方法**

使用形状样式设置包含视图的演示背景。

## 声明

```swift
nonisolated func presentationBackground<S>(_ style: S) -> some View where S : ShapeStyle

```

## 参数

- **style**：用作演示背景的形状样式。

## 说明

以下示例使用 [thick](../Material/thick.zh-Hans.md) 材质作为视图背景：

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationBackground(.thickMaterial)
        }
    }
}
```

`presentationBackground(_:)` 修饰符与 [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md) 修饰符在几个关键方面有所不同。演示文稿背景：

- 自动填充整个演示文稿。

- 在支持的平台上，允许演示文稿后面的视图以半透明样式显示。

## 设置工作表及其背景的样式

- **presentationCornerRadius(_:)**：请求演示文稿具有特定的圆角半径。

- **presentationBackground(alignment:content:)**：将包含工作表的演示文稿背景设置为自定义视图。

- **presentationBackgroundInteraction(_:)**：控制用户是否可以与演示文稿后面的视图进行交互。

- **PresentationBackgroundInteraction**：演示文稿后面的视图可用的交互类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationBackground(_:)
crawled: 2025-12-02T17:30:20Z
---

# presentationBackground(_:)

**Instance Method**

Sets the presentation background of the enclosing sheet using a shape style.

## Declaration

```swift
nonisolated func presentationBackground<S>(_ style: S) -> some View where S : ShapeStyle

```

## Parameters

- **style**: The shape style to use as the presentation background.

## Discussion

The following example uses the [thick](../Material/thick.zh-Hans.md) material as the sheet background:

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationBackground(.thickMaterial)
        }
    }
}
```

The `presentationBackground(_:)` modifier differs from the [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md) modifier in several key ways. A presentation background:

- Automatically fills the entire presentation.
- Allows views behind the presentation to show through translucent styles on supported platforms.



## Styling a sheet and its background

- **presentationCornerRadius(_:)**: Requests that the presentation have a specific corner radius.
- **presentationBackground(alignment:content:)**: Sets the presentation background of the enclosing sheet to a custom view.
- **presentationBackgroundInteraction(_:)**: Controls whether people can interact with the view behind a presentation.
- **PresentationBackgroundInteraction**: The kinds of interaction available to views behind a presentation.

