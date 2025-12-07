---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/indices(in:)
抓取时间： 2025-12-03T06:17:46Z
---

# indices(in:)

**实例方法**

当前文本选择索引。

## 声明

```swift
func indices(in text: AttributedString) -> AttributedTextSelection.Indices
```

## 返回值

如果对给定的`text` 有效，则返回当前选择，否则返回一个有效的后备索引。

## 讨论

始终确保选区和文本保持同步。使用 `Foundation/AttributedString/transform(updating:body:)`、`Foundation/AttributedString/transformAttributes(in:body:)` 或 `Foundation/AttributedString/replaceSelection(_:with:)`可自动做到这一点。

在对文本进行编程更改后，手动将选区重置为新初始化的选区，此时选区不应随字符移动。

```swift
struct ContentView: View {
    @State private var text = AttributedString()
    @State private var selection = AttributedTextSelection()

    var body: some View {
        TextEditor(text: $text, selection: $selection)

        Button("Insert Date") {
            text.replaceSelection(
                &selection,
                withCharacters: Date.now.formatted())
        }

        Button("Reset") {
            text = "Hello, World!"
            selection = .init(range: text.startIndex..<text.endIndex)
        }
    }
}
```

有关属性字符串索引有效性的详细信息，请参见 [doc://com.apple.documentation/documentation/Foundation/AttributedString/Index/isValid(within:)-8fw50]。


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/indices(in:)
crawled: 2025-12-03T06:17:46Z
---

# indices(in:)

**Instance Method**

The current text selection indices.

## Declaration

```swift
func indices(in text: AttributedString) -> AttributedTextSelection.Indices
```

## Return Value

The current selection if valid for the given `text` or a valid fallback index otherwise.

## Discussion

Always make sure to keep selection and text synchronized. Use `Foundation/AttributedString/transform(updating:body:)`, `Foundation/AttributedString/transformAttributes(in:body:)` or `Foundation/AttributedString/replaceSelection(_:with:)` to do so automatically.

Reset your selection manually to a newly initialized one after making programmatic changes to the text where the selection should not just move with the characters.

```swift
struct ContentView: View {
    @State private var text = AttributedString()
    @State private var selection = AttributedTextSelection()

    var body: some View {
        TextEditor(text: $text, selection: $selection)

        Button("Insert Date") {
            text.replaceSelection(
                &selection,
                withCharacters: Date.now.formatted())
        }

        Button("Reset") {
            text = "Hello, World!"
            selection = .init(range: text.startIndex..<text.endIndex)
        }
    }
}
```

For more details on attributed string index validity, see [doc://com.apple.documentation/documentation/Foundation/AttributedString/Index/isValid(within:)-8fw50].

