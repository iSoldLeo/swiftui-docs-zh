--- 来源：https://developer.apple.com/documentation/SwiftUI/View/documentBrowserContextMenu(_:)

抓取时间：2025-11-30T21:08:37Z

---

# documentBrowserContextMenu(_:)

**实例方法**

为文档浏览器添加接受已选文件列表作为参数的操作。

## 声明

```swift
@MainActor @preconcurrency func documentBrowserContextMenu(@ViewBuilder _ menu: @escaping ([URL]?) -> some View) -> some View

```

## 参数

- **menu**：表示菜单内容的项。

## 说明

为文档浏览器项添加修饰符 `documentBrowserContextMenu`，以提供其他操作。例如，书籍编辑器应用程序可以添加一个“收藏”按钮，用于将用户选择的书籍标记为收藏。当用户将浏览器切换到“选择”模式时，此按钮启用。

```swift
import UniformTypeIdentifiers

struct BookEditor: View {

    var body: some View {
        DocumentLaunchView(for: [.book]) {
            NewDocumentButton("Start New Book")
        } onDocumentOpen: { url in
            BookEditor(url)
        }
        .documentBrowserContextMenu { selectedURLs in
            FavoriteBookButton(urls: selectedURLs)
        }
    }
}

struct FavoriteBookButton: View {
    var urls: [URL]?
    var body: some View {
        Button {
            updateFavorite(urls)
        } label: {
            Image(systemName: allFavorite(urls) ? "heart.fill" : "heart")
        }
    }

    func allFavorite(_ urls: [URL]?) -> Bool { ... }
    func updateFavorite(_ urls: [URL]?) { ... }
}

struct BookEditor: View {
    init(_ url: URL) { ... }
}

extension UTType {
    static let book = UTType(exportedAs: "com.example.bookEditor")
}
```

在上面的示例中，应用程序存储了一个收藏书籍的 URL 列表，无需访问磁盘上的文件。如果应用程序需要从磁盘读取 URL 的内容或关联的元数据，则应调用 `URL.startAccessingSecurityScopedResource()` 来获取资源访问权限，并在不再需要访问权限时调用 `URL.stopAccessingSecurityScopedResource()` 来放弃访问权限。

当文档浏览器处于选择模式时，这些操作会显示在文档浏览器的导航栏中，并且还会添加到文件项的上下文菜单中。


---
source: https://developer.apple.com/documentation/SwiftUI/View/documentBrowserContextMenu(_:)
crawled: 2025-11-30T21:08:37Z
---

# documentBrowserContextMenu(_:)

**Instance Method**

Adds to a `DocumentLaunchView` actions that accept a list of selected files as their parameter.

## Declaration

```swift
@MainActor @preconcurrency func documentBrowserContextMenu(@ViewBuilder _ menu: @escaping ([URL]?) -> some View) -> some View

```

## Parameters

- **menu**: Items representing the content of the menu.

## Discussion

Add `documentBrowserContextMenu` modifier to [DocumentLaunchView](../DocumentLaunchView.zh-Hans.md) to provide additional actions to the document browser items’ context menu. For example, a book editor application could have a “Favorite” button that marks user-chosen books as their favorite. The button enables when the user switches the browser into “Selection” mode.

```swift
import UniformTypeIdentifiers

struct BookEditor: View {

    var body: some View {
        DocumentLaunchView(for: [.book]) {
            NewDocumentButton("Start New Book")
        } onDocumentOpen: { url in
            BookEditor(url)
        }
        .documentBrowserContextMenu { selectedURLs in
            FavoriteBookButton(urls: selectedURLs)
        }
    }
}

struct FavoriteBookButton: View {
    var urls: [URL]?
    var body: some View {
        Button {
            updateFavorite(urls)
        } label: {
            Image(systemName: allFavorite(urls) ? "heart.fill" : "heart")
        }
    }

    func allFavorite(_ urls: [URL]?) -> Bool { ... }
    func updateFavorite(_ urls: [URL]?) { ... }
}

struct BookEditor: View {
    init(_ url: URL) { ... }
}

extension UTType {
    static let book = UTType(exportedAs: "com.example.bookEditor")
}
```

In the example above, the application stores a list of URLs to favorite books, and does not need to access the file on disk. In cases when an application wants to read the contents of the URL from the disk or associated metadata, it should call `URL.startAccessingSecurityScopedResource()` to gain access to the resource, and `URL.stopAccessingSecurityScopedResource()` to relinquish access when it is not needed.

The actions are displayed in the document browser navigation bar when a document browser is in Select mode, and also added to context menu for the file items.

