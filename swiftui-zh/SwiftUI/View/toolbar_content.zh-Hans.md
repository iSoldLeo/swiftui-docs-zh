--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbar(content:)

抓取时间：2025-11-30T21:16:08Z

---

# toolbar(content:)

**实例方法**

使用指定的项目填充工具栏或导航栏。

## 声明

```swift
nonisolated func toolbar<Content>(@ToolbarContentBuilder content: () -> Content) -> some View where Content : ToolbarContent

```

## 参数

- **content**：表示工具栏内容的项目。

## 说明

使用此方法可将您提供给工具栏视图构建器的视图集合填充到工具栏中。

工具栏修饰符需要一个工具栏项目集合，您可以通过两种方式提供：一种是提供一个视图集合，其中每个视图都包装在 [ToolbarItem](../ToolbarItem.zh-Hans.md) 中；另一种是提供一个视图集合，作为 [ToolbarItemGroup](../ToolbarItemGroup.zh-Hans.md) 提供。以下示例使用一组 [ToolbarItem](../ToolbarItem.zh-Hans.md) 视图来创建一个支持文本编辑功能的 macOS 工具栏：

```swift
struct StructToolbarItemGroupView: View {
    @State private var text = ""
    @State private var bold = false
    @State private var italic = false
    @State private var fontSize = 12.0

    var displayFont: Font {
        let font = Font.system(size: CGFloat(fontSize),
                               weight: bold == true ? .bold : .regular)
        return italic == true ? font.italic() : font
    }

    var body: some View {
        TextEditor(text: $text)
            .font(displayFont)
            .toolbar {
                ToolbarItemGroup {
                    Slider(
                        value: $fontSize,
                        in: 8...120,
                        minimumValueLabel:
                            Text("A").font(.system(size: 8)),
                        maximumValueLabel:
                            Text("A").font(.system(size: 16))
                    ) {
                        Text("Font Size (\(Int(fontSize)))")
                    }
                    .frame(width: 150)
                    Toggle(isOn: $bold) {
                        Image(systemName: "bold")
                    }
                    Toggle(isOn: $italic) {
                        Image(systemName: "italic")
                    }
                }
            }
            .navigationTitle("My Note")
    }
}
```

虽然并非强制要求，但将一组相关的工具栏项目包装在 [ToolbarItemGroup](../ToolbarItemGroup.zh-Hans.md) 中，可以实现控件和工具栏项目之间的一一对应关系，从而确保在每个平台上都能获得正确的布局和间距。有关工具栏的设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/toolbars]。

## 填充工具栏

- **ToolbarItem**：表示可放置在工具栏或导航栏中的项目的模型。

- **ToolbarItemGroup**：表示可放置在工具栏或导航栏中的一组 `ToolbarItem` 的模型。

- **ToolbarItemPlacement**：定义工具栏项位置的结构。

- **ToolbarContent**：符合规范的类型表示可以放置在工具栏中不同位置的项。

- **ToolbarContentBuilder**：从多表达式闭包构造工具栏项集。

- **ToolbarSpacer**：工具栏中的标准空间项。

- **DefaultToolbarItem**：表示系统组件的工具栏项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbar(content:)
crawled: 2025-11-30T21:16:08Z
---

# toolbar(content:)

**Instance Method**

Populates the toolbar or navigation bar with the specified items.

## Declaration

```swift
nonisolated func toolbar<Content>(@ToolbarContentBuilder content: () -> Content) -> some View where Content : ToolbarContent

```

## Parameters

- **content**: The items representing the content of the toolbar.

## Discussion

Use this method to populate a toolbar with a collection of views that you provide to a toolbar view builder.

The toolbar modifier expects a collection of toolbar items which you can provide either by supplying a collection of views with each view wrapped in a [ToolbarItem](../ToolbarItem.zh-Hans.md), or by providing a collection of views as a [ToolbarItemGroup](../ToolbarItemGroup.zh-Hans.md). The example below uses a collection of [ToolbarItem](../ToolbarItem.zh-Hans.md) views to create a macOS toolbar that supports text editing features:

```swift
struct StructToolbarItemGroupView: View {
    @State private var text = ""
    @State private var bold = false
    @State private var italic = false
    @State private var fontSize = 12.0

    var displayFont: Font {
        let font = Font.system(size: CGFloat(fontSize),
                               weight: bold == true ? .bold : .regular)
        return italic == true ? font.italic() : font
    }

    var body: some View {
        TextEditor(text: $text)
            .font(displayFont)
            .toolbar {
                ToolbarItemGroup {
                    Slider(
                        value: $fontSize,
                        in: 8...120,
                        minimumValueLabel:
                            Text("A").font(.system(size: 8)),
                        maximumValueLabel:
                            Text("A").font(.system(size: 16))
                    ) {
                        Text("Font Size (\(Int(fontSize)))")
                    }
                    .frame(width: 150)
                    Toggle(isOn: $bold) {
                        Image(systemName: "bold")
                    }
                    Toggle(isOn: $italic) {
                        Image(systemName: "italic")
                    }
                }
            }
            .navigationTitle("My Note")
    }
}
```



Although it’s not mandatory, wrapping a related group of toolbar items together in a [ToolbarItemGroup](../ToolbarItemGroup.zh-Hans.md) provides a one-to-one mapping between controls and toolbar items which results in the correct layout and spacing on each platform. For design guidance on toolbars, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/toolbars] in the Human Interface Guidelines.

## Populating a toolbar

- **ToolbarItem**: A model that represents an item which can be placed in the toolbar or navigation bar.
- **ToolbarItemGroup**: A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.
- **ToolbarItemPlacement**: A structure that defines the placement of a toolbar item.
- **ToolbarContent**: Conforming types represent items that can be placed in various locations in a toolbar.
- **ToolbarContentBuilder**: Constructs a toolbar item set from multi-expression closures.
- **ToolbarSpacer**: A standard space item in toolbars.
- **DefaultToolbarItem**: A toolbar item that represents a system component.

