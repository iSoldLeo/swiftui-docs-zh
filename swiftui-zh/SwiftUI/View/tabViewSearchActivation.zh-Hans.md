---

来源：https://developer.apple.com/documentation/SwiftUI/View/tabViewSearchActivation(_:)

抓取时间：2025-12-02T17:26:02Z

---

# tabViewSearchActivation(_:)

**实例方法**

配置搜索标签页中搜索功能的激活和停用行为。

## 声明

```swift
nonisolated func tabViewSearchActivation(_ activation: TabSearchActivation) -> some View

```

## 说明

在 [TabView](../TabView.zh-Hans.md) 上使用此修饰符可以更改搜索激活的处理方式。具体的激活行为取决于传递给此修饰符的 [TabSearchActivation](../TabSearchActivation.zh-Hans.md)：

```swift
struct TabExampleView: View {
    @State private var text: String = ""

    var body: some View {
        TabView {
            Tab("Books", systemImage: "book") {
                BooksTab()
            }
            Tab(role: .search) {
                NavigationStack {
                    SearchContent()
                }
            }
        }
        .searchable(text: $text)
        .tabViewSearchActivation(.searchTabSelection)
    }
}
```

默认情况下，搜索功能仅由用户激活和停用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tabViewSearchActivation(_:)
crawled: 2025-12-02T17:26:02Z
---

# tabViewSearchActivation(_:)

**Instance Method**

Configures the activation and deactivation behavior of search in the search tab.

## Declaration

```swift
nonisolated func tabViewSearchActivation(_ activation: TabSearchActivation) -> some View

```

## Discussion

Use this modifier on a [TabView](../TabView.zh-Hans.md) to change how search activation is handled. The exact activation behavior is determined by the [TabSearchActivation](../TabSearchActivation.zh-Hans.md) you pass to this modifier:

```swift
struct TabExampleView: View {
    @State private var text: String = ""

    var body: some View {
        TabView {
            Tab("Books", systemImage: "book") {
                BooksTab()
            }
            Tab(role: .search) {
                NavigationStack {
                    SearchContent()
                }
            }
        }
        .searchable(text: $text)
        .tabViewSearchActivation(.searchTabSelection)
    }
}
```

By default, search is only activated and deactivated by the user.

