--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchSelection(_:)

抓取时间：2025-12-02T17:25:19Z

---

# searchSelection(_:)

**实例方法**

将与最近的可搜索修饰符关联的搜索字段的选择绑定到给定的 [TextSelection](../TextSelection.zh-Hans.md) 值。

## 声明

```swift
nonisolated func searchSelection(_ selection: Binding<TextSelection?>) -> some View

```

## 参数

- **selection**：要绑定的选择值。

## 说明

使用此修饰符读取和设置搜索界面中的选择。选择使用 `TextSelection` 表示，其中索引相对于您在 [searchable(text:placement:prompt:)](searchable_text_placement_prompt.zh-Hans.md) 修饰符中提供的搜索文本。请注意，此值不会代表文本之外的选中状态，例如任何前导标记。

SwiftUI 会在用户更改选择状态（例如通过输入）时自动更新此值。同样，您也可以通过写入此值来更改选择状态。

以下示例创建了一个搜索界面，该界面会在获得焦点时选中所有文本。

```swift
struct ContentView: View {
    @State var text = "Hello, world!"
    @State var selection: TextSelection?
    @FocusState var focused

    var body: some View {
        NavigationSplitView {
            Sidebar()
                .searchable(text: $text)
                .searchFocused($focused)
                .searchSelection($selection)
        } detail: {
            Detail()
        }
        .onChange(of: focused) {
            if focused {
                selection = TextSelection(
                    range: text.startIndex..<text.endIndex)
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchSelection(_:)
crawled: 2025-12-02T17:25:19Z
---

# searchSelection(_:)

**Instance Method**

Binds the selection of the search field associated with the nearest searchable modifier to the given [TextSelection](../TextSelection.zh-Hans.md) value.

## Declaration

```swift
nonisolated func searchSelection(_ selection: Binding<TextSelection?>) -> some View

```

## Parameters

- **selection**: The selection value to bind.

## Discussion

Use this modifier to read and set selection in your search interface. Selection is represented using `TextSelection` where the indices are relative to the search text you provide on the [searchable(text:placement:prompt:)](searchable_text_placement_prompt.zh-Hans.md) modifier. Note that this value will not represent selection outside of the text, such as in any leading tokens.

SwiftUI will automatically update this value when the user changes selection, such as by typing. Likewise, you can change selection by writing to this value.

The following example creates a search interface that selects all of the text on focus.

```swift
struct ContentView: View {
    @State var text = "Hello, world!"
    @State var selection: TextSelection?
    @FocusState var focused

    var body: some View {
        NavigationSplitView {
            Sidebar()
                .searchable(text: $text)
                .searchFocused($focused)
                .searchSelection($selection)
        } detail: {
            Detail()
        }
        .onChange(of: focused) {
            if focused {
                selection = TextSelection(
                    range: text.startIndex..<text.endIndex)
            }
        }
    }
}
```

