---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/newItem
抓取时间： 2025-12-03T06:23:37Z
---

# newItem

**类型属性**

用于放置创建不同类型文档的命令。

## 声明

```swift
static let newItem: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包括以下命令：

- 新建

## 文件操作

- **importExport**：放置与使用应用程序本机不支持的格式导入和导出数据有关的命令。
- **printItem**：放置与打印应用程序内容相关的命令。
- **saveItem**：保存打开的文档和关闭窗口的命令的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/newItem
crawled: 2025-12-03T06:23:37Z
---

# newItem

**Type Property**

Placement for commands that create different kinds of documents.

## Declaration

```swift
static let newItem: CommandGroupPlacement
```

## Discussion

By default, this group includes the following commands in macOS:

- New

## File manipulation

- **importExport**: Placement for commands that relate to importing and exporting data using formats that the app doesn’t natively support.
- **printItem**: Placement for commands related to printing app content.
- **saveItem**: Placement for commands that save open documents and close windows.

