--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchSuggestionsPlacement/automatic
抓取时间：2025-12-03T06:05:28Z

---

# automatic

**类型属性**

搜索建议会根据周围环境自动渲染。

## 声明

```swift
static var automatic: SearchSuggestionsPlacement { get }
```

## 讨论

不同平台的行为有所不同：

- 在 iOS 和 iPadOS 中，搜索建议会以列表的形式覆盖在应用的主要内容之上。

- 在 macOS 中，搜索建议会以菜单的形式呈现。

- 在 tvOS 中，搜索建议会以行的形式显示在搜索框下方。

- 在 watchOS 中，搜索建议会以列表的形式添加到包含它的导航堆栈中。

## 获取位置

- **content**：搜索建议会显示在应用的主要内容中。

- **menu**：搜索建议会显示在与搜索框关联的菜单中。


---
source: https://developer.apple.com/documentation/SwiftUI/SearchSuggestionsPlacement/automatic
crawled: 2025-12-03T06:05:28Z
---

# automatic

**Type Property**

Search suggestions render automatically based on the surrounding context.

## Declaration

```swift
static var automatic: SearchSuggestionsPlacement { get }
```

## Discussion

The behavior varies by platform:

- In iOS and iPadOS, suggestions render as a list overlaying the main content of the app.
- In macOS, suggestions render in a menu.
- In tvOS, suggestions render as a row underneath the search field.
- In watchOS, suggestions render in a list pushed onto the containing navigation stack.

## Getting placements

- **content**: Search suggestions render in the main content of the app.
- **menu**: Search suggestions render inside of a menu attached to the search field.

