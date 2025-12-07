--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/documentBrowserContextMenu(_:)

抓取时间：2025-12-03T05:31:09Z

---

# documentBrowserContextMenu(_:)

**实例方法**

向 `DocumentGroupLaunchScene` 添加接受已选文件列表作为参数的操作。

## 声明

```swift
@MainActor @preconcurrency func documentBrowserContextMenu(@ViewBuilder _ menu: @escaping ([URL]?) -> some View) -> some Scene

```

## 参数

- **menu**：表示菜单内容的项。

## 说明

当文档浏览器处于选择模式时，这些操作会显示在文档浏览器的导航栏中，并且也会添加到文件项的上下文菜单中。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/documentBrowserContextMenu(_:)
crawled: 2025-12-03T05:31:09Z
---

# documentBrowserContextMenu(_:)

**Instance Method**

Adds to a `DocumentGroupLaunchScene` actions that accept a list of selected files as their parameter.

## Declaration

```swift
@MainActor @preconcurrency func documentBrowserContextMenu(@ViewBuilder _ menu: @escaping ([URL]?) -> some View) -> some Scene

```

## Parameters

- **menu**: Items representing the content of the menu.

## Discussion

The actions are displayed in the document browser navigation bar when a document browser is in Select mode, and also added to context menu for the file items.

