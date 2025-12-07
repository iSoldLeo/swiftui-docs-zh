--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbar(id:content:)

抓取时间：2025-12-02T17:31:09Z

---

# toolbar(id:content:)

**实例方法**

使用指定的项目填充工具栏或导航栏，允许用户进行自定义。

## 声明

```swift
nonisolated func toolbar<Content>(id: String, @ToolbarContentBuilder content: () -> Content) -> some View where Content : CustomizableToolbarContent

```

## 参数

- **id**：此工具栏的唯一标识符。

- **content**：表示工具栏内容的 content。

## 说明

当您希望允许用户自定义工具栏中元素的组件和布局时，请使用此修饰符。toolbar 修饰符需要一个工具栏项目集合，您可以通过提供一个视图集合来提供该集合，其中每个视图都包含在 [ToolbarItem](../ToolbarItem.zh-Hans.md) 中。以下示例创建了一个视图，该视图表示每个 [ToolbarItem](../ToolbarItem.zh-Hans.md) 以及一个唯一标识工具栏项的 ID，以便将其添加到自定义编辑器中：

```swift
struct ToolsEditorView: View {
    @State private var text = ""
    @State private var bold = false
    @State private var italic = false
    @State private var fontSize = 12.0

    var displayFont: Font {
        let font = Font.system(
           size: CGFloat(fontSize),
             weight: bold == true ? .bold : .regular)
        return italic == true ? font.italic() : font
    }

    var body: some View {
        TextEditor(text: $text)
            .font(displayFont)
            .toolbar(id: "editingtools") {
                ToolbarItem(
                    id: "sizeSelector", placement: .secondaryAction
                ) {
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
                }
                ToolbarItem(
                    id: "bold", placement: .secondaryAction
                ) {
                    Toggle(isOn: $bold) {
                        Image(systemName: "bold")
                    }
                }
                ToolbarItem(
                    id: "italic", placement: .secondaryAction
                ) {
                    Toggle(isOn: $italic) {
                        Image(systemName: "italic")
                    }
                }
            }
            .navigationTitle("My Note")
    }
}
```

在 macOS 中，您可以使用场景修改器 [commands(content:)](../scene/commands_content.zh-Hans.md) 将 [ToolbarCommands](../ToolbarCommands.zh-Hans.md) 实例添加到场景中，从而启用工具栏自定义的菜单支持：

```swift
@main
struct ToolbarContent_macOSApp: App {
    var body: some Scene {
        WindowGroup {
            ToolsEditorView()
                .frame(maxWidth: .infinity, maxHeight: .infinity)
        }
        .commands {
            ToolbarCommands()
        }
    }
}
```

添加工具栏命令后，系统会在应用程序的主菜单中添加一个菜单项，以提供工具栏自定义支持。此外，您还可以按住 Control 键并单击工具栏来打开工具栏自定义编辑器。

## 填充可自定义工具栏

- **CustomizableToolbarContent**：符合规范的类型表示可以放置在可自定义工具栏中不同位置的项。

- **ToolbarCustomizationBehavior**：可自定义工具栏内容的自定义行为。

- **ToolbarCustomizationOptions**：影响可自定义工具栏内容默认自定义行为的选项。

- **SearchToolbarBehavior**：工具栏中搜索字段的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbar(id:content:)
crawled: 2025-12-02T17:31:09Z
---

# toolbar(id:content:)

**Instance Method**

Populates the toolbar or navigation bar with the specified items, allowing for user customization.

## Declaration

```swift
nonisolated func toolbar<Content>(id: String, @ToolbarContentBuilder content: () -> Content) -> some View where Content : CustomizableToolbarContent

```

## Parameters

- **id**: A unique identifier for this toolbar.
- **content**: The content representing the content of the toolbar.

## Discussion

Use this modifier when you want to allow the user to customize the components and layout of elements in the toolbar. The toolbar modifier expects a collection of toolbar items which you can provide either by supplying a collection of views with each view wrapped in a [ToolbarItem](../ToolbarItem.zh-Hans.md).



The example below creates a view that represents each [ToolbarItem](../ToolbarItem.zh-Hans.md) along with an ID that uniquely identifies the toolbar item to the customization editor:

```swift
struct ToolsEditorView: View {
    @State private var text = ""
    @State private var bold = false
    @State private var italic = false
    @State private var fontSize = 12.0

    var displayFont: Font {
        let font = Font.system(
           size: CGFloat(fontSize),
             weight: bold == true ? .bold : .regular)
        return italic == true ? font.italic() : font
    }

    var body: some View {
        TextEditor(text: $text)
            .font(displayFont)
            .toolbar(id: "editingtools") {
                ToolbarItem(
                    id: "sizeSelector", placement: .secondaryAction
                ) {
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
                }
                ToolbarItem(
                    id: "bold", placement: .secondaryAction
                ) {
                    Toggle(isOn: $bold) {
                        Image(systemName: "bold")
                    }
                }
                ToolbarItem(
                    id: "italic", placement: .secondaryAction
                ) {
                    Toggle(isOn: $italic) {
                        Image(systemName: "italic")
                    }
                }
            }
            .navigationTitle("My Note")
    }
}
```





In macOS you can enable menu support for toolbar customization by adding a [ToolbarCommands](../ToolbarCommands.zh-Hans.md) instance to a scene using the [commands(content:)](../scene/commands_content.zh-Hans.md) scene modifier:

```swift
@main
struct ToolbarContent_macOSApp: App {
    var body: some Scene {
        WindowGroup {
            ToolsEditorView()
                .frame(maxWidth: .infinity, maxHeight: .infinity)
        }
        .commands {
            ToolbarCommands()
        }
    }
}
```

When you add the toolbar commands, the system adds a menu item to your app’s main menu to provide toolbar customization support. This is in addition to the ability to Control-click on the toolbar to open the toolbar customization editor.



## Populating a customizable toolbar

- **CustomizableToolbarContent**: Conforming types represent items that can be placed in various locations in a customizable toolbar.
- **ToolbarCustomizationBehavior**: The customization behavior of customizable toolbar content.
- **ToolbarCustomizationOptions**: Options that influence the default customization behavior of customizable toolbar content.
- **SearchToolbarBehavior**: The behavior of a search field in a toolbar.

