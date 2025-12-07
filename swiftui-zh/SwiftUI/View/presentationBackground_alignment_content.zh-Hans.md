--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationBackground(alignment:content:)

抓取时间：2025-11-30T21:15:20Z

---

# presentationBackground(alignment:content:)

**实例方法**

将包含视图的演示背景设置为自定义视图。

## 声明

```swift
nonisolated func presentationBackground<V>(alignment: Alignment = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## 参数

- **alignment**：修饰符用于定位隐式 [ZStack](../ZStack.zh-Hans.md)（用于分组背景视图）的对齐方式。默认值为 [center](../Alignment/center.zh-Hans.md)。

- **content**：用作演示背景的视图。

## 讨论

以下示例使用黄色视图作为工作表背景：

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationBackground {
                    Color.yellow
                }
        }
    }
}
```

`presentationBackground(alignment:content:)` 修饰符与 [background(alignment:content:)](background_alignment_content.zh-Hans.md) 修饰符在几个关键方面有所不同。演示背景：

- 自动填充整个演示区域。

- 在支持的平台上，允许演示区域后面的视图透过 `content` 的半透明区域显示出来。

## 设置工作表及其背景的样式

- **presentationCornerRadius(_:)**：请求演示区域具有特定的圆角半径。

- **presentationBackground(_:)**：使用形状样式设置包含工作表的演示背景。

- **presentationBackgroundInteraction(_:)**：控制用户是否可以与演示区域后面的视图进行交互。

- **PresentationBackgroundInteraction**：演示文稿背后的视图可用的交互类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationBackground(alignment:content:)
crawled: 2025-11-30T21:15:20Z
---

# presentationBackground(alignment:content:)

**Instance Method**

Sets the presentation background of the enclosing sheet to a custom view.

## Declaration

```swift
nonisolated func presentationBackground<V>(alignment: Alignment = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## Parameters

- **alignment**: The alignment that the modifier uses to position the implicit [ZStack](../ZStack.zh-Hans.md) that groups the background views. The default is [center](../Alignment/center.zh-Hans.md).
- **content**: The view to use as the background of the presentation.

## Discussion

The following example uses a yellow view as the sheet background:

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationBackground {
                    Color.yellow
                }
        }
    }
}
```

The `presentationBackground(alignment:content:)` modifier differs from the [background(alignment:content:)](background_alignment_content.zh-Hans.md) modifier in several key ways. A presentation background:

- Automatically fills the entire presentation.
- Allows views behind the presentation to show through translucent areas of the `content` on supported platforms.



## Styling a sheet and its background

- **presentationCornerRadius(_:)**: Requests that the presentation have a specific corner radius.
- **presentationBackground(_:)**: Sets the presentation background of the enclosing sheet using a shape style.
- **presentationBackgroundInteraction(_:)**: Controls whether people can interact with the view behind a presentation.
- **PresentationBackgroundInteraction**: The kinds of interaction available to views behind a presentation.

