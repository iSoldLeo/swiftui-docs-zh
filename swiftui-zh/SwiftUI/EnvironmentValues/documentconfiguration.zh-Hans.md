---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/documentconfiguration
抓取时间： 2025-12-03T05:59:01Z
---

# 文档配置

**实例属性**

[DocumentGroup](../DocumentGroup.zh-Hans.md)中文档的配置。

## 声明

```swift
var documentConfiguration: DocumentConfiguration? { get }
```

## 讨论

对于未被 [DocumentGroup](../DocumentGroup.zh-Hans.md) 包围的视图，其值为`nil`。

例如，如果应用程序在每个文档的页脚显示文档路径，它可以从环境中获取 URL：

```swift
struct ContentView: View {
    @Binding var document: TextDocument
    @Environment(\.documentConfiguration) private var configuration: DocumentConfiguration?

    var body: some View {
        …
        Label(
            configuration?.fileURL?.path ??
                "", systemImage: "folder.circle"
        )
    }
}
```

## 访问文档配置

- **DocumentConfiguration**


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/documentconfiguration
crawled: 2025-12-03T05:59:01Z
---

# documentConfiguration

**Instance Property**

The configuration of a document in a [DocumentGroup](../DocumentGroup.zh-Hans.md).

## Declaration

```swift
var documentConfiguration: DocumentConfiguration? { get }
```

## Discussion

The value is `nil` for views that are not enclosed in a [DocumentGroup](../DocumentGroup.zh-Hans.md).

For example, if the app shows the document path in the footer of each document, it can get the URL from the environment:

```swift
struct ContentView: View {
    @Binding var document: TextDocument
    @Environment(\.documentConfiguration) private var configuration: DocumentConfiguration?

    var body: some View {
        …
        Label(
            configuration?.fileURL?.path ??
                "", systemImage: "folder.circle"
        )
    }
}
```

## Accessing document configuration

- **DocumentConfiguration**

