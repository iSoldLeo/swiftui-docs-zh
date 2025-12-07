---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/searchSuggestionsPlacement
抓取时间： 2025-12-03T06:07:13Z
---

# searchSuggestionsPlacement

**实例属性**

搜索建议的当前位置。

## 声明

```swift
var searchSuggestionsPlacement: SearchSuggestionsPlacement { get }
```

## 讨论

搜索建议根据平台和周围环境呈现，您可以在其中放置包含建议的可搜索修饰符。您可以通过两种方式呈现搜索建议：

- 在搜索栏的菜单中。
- 与应用程序的主要内容内联。

通过查询搜索建议中的[searchSuggestionsPlacement](searchSuggestionsPlacement.zh-Hans.md)，您可以找到当前的搜索建议位置。

```swift
enum FruitSuggestion: String, Identifiable {
    case apple, banana, orange
    var id: Self { self }
}

@State private var text: String = ""
@State private var suggestions: [FruitSuggestion] = []

var body: some View {
    MainContent()
        .searchable(text: $text) {
            FruitSuggestions(suggestions: suggestions)
        }
}

struct FruitSuggestions: View {
    var suggestions: [FruitSuggestion]

    @Environment(\.searchSuggestionsPlacement)
    private var placement

    var body: some View {
        if shouldRender {
            ForEach(suggestions) { suggestion in
                Text(suggestion.rawValue.capitalized)
                    .searchCompletion(suggestion.rawValue)
            }
        }
    }

    var shouldRender: Bool {
        #if os(iOS)
        placement == .menu
        #else
        true
        #endif
    }
}
```

在上例中，只有当可搜索修饰符在菜单中显示搜索建议时，搜索建议才会在 iOS 中呈现。当搜索结果在列表中显示时，您可能希望在自己的列表中与自己的搜索结果一起显示建议。

## 控制和输入

- **buttonRepeatBehavior**：与此环境关联的按钮是否应在长时间交互时重复触发其动作。
- **controlSize**：适用于视图中控件的大小。
- **defaultWheelPickerItemHeight**：视图中控件的默认高度：滚轮式选取器（如日期选取器）中项目的默认高度。
- **keyboardShortcut**：在此环境中触发按钮的键盘快捷键。
- **menuIndicatorVisibility**：应用于视图中控件的菜单指示器可见性。
- **menuOrder**：从该视图显示的菜单项目的首选顺序。
- **preferredPencilDoubleTapAction**：用户在 "设置 "应用中选择双击 Apple Pencil 后希望执行的操作。
- **preferredPencilSqueezeAction**：用户在设置 app 中选择的挤压 Apple Pencil 时喜欢执行的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/searchSuggestionsPlacement
crawled: 2025-12-03T06:07:13Z
---

# searchSuggestionsPlacement

**Instance Property**

The current placement of search suggestions.

## Declaration

```swift
var searchSuggestionsPlacement: SearchSuggestionsPlacement { get }
```

## Discussion

Search suggestions render based on the platform and surrounding context in which you place the searchable modifier containing suggestions. You can render search suggestions in two ways:

- In a menu attached to the search field.
- Inline with the main content of the app.

You find the current search suggestion placement by querying the [searchSuggestionsPlacement](searchSuggestionsPlacement.zh-Hans.md) in your search suggestions.

```swift
enum FruitSuggestion: String, Identifiable {
    case apple, banana, orange
    var id: Self { self }
}

@State private var text: String = ""
@State private var suggestions: [FruitSuggestion] = []

var body: some View {
    MainContent()
        .searchable(text: $text) {
            FruitSuggestions(suggestions: suggestions)
        }
}

struct FruitSuggestions: View {
    var suggestions: [FruitSuggestion]

    @Environment(\.searchSuggestionsPlacement)
    private var placement

    var body: some View {
        if shouldRender {
            ForEach(suggestions) { suggestion in
                Text(suggestion.rawValue.capitalized)
                    .searchCompletion(suggestion.rawValue)
            }
        }
    }

    var shouldRender: Bool {
        #if os(iOS)
        placement == .menu
        #else
        true
        #endif
    }
}
```

In the above example, search suggestions only render in iOS if the searchable modifier displays them in a menu. You might want to do this to render suggestions in your own list alongside your own search results when they would render in a list.

## Controls and input

- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **controlSize**: The size to apply to controls within a view.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **keyboardShortcut**: The keyboard shortcut that buttons in this environment will be triggered with.
- **menuIndicatorVisibility**: The menu indicator visibility to apply to controls within a view.
- **menuOrder**: The preferred order of items for menus presented from this view.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.

