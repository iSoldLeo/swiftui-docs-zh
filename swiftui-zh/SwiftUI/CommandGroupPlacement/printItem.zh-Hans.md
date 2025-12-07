---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/printItem
抓取时间： 2025-12-03T06:23:38Z
---

# 打印项目

**类型属性**

与打印应用程序内容相关的命令的位置。

## 声明

```swift
static let printItem: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包括以下命令：

- 页面设置
- 打印

## 文件操作

- **importExport**：放置与使用应用程序本机不支持的格式导入和导出数据有关的命令。
- **newItem**：放置创建不同类型文档的命令。
- **saveItem**：保存打开的文档和关闭窗口的命令的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/printItem
crawled: 2025-12-03T06:23:38Z
---

# printItem

**Type Property**

Placement for commands related to printing app content.

## Declaration

```swift
static let printItem: CommandGroupPlacement
```

## Discussion

By default, this group includes the following commands in macOS:

- Page Setup
- Print

## File manipulation

- **importExport**: Placement for commands that relate to importing and exporting data using formats that the app doesn’t natively support.
- **newItem**: Placement for commands that create different kinds of documents.
- **saveItem**: Placement for commands that save open documents and close windows.

