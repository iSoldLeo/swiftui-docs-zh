---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/saveItem
抓取时间： 2025-12-03T06:23:39Z
---

# 保存项目

**类型属性**

用于保存打开的文档和关闭窗口的命令。

## 声明

```swift
static let saveItem: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包括以下命令：

- 关闭
- 保存
- 保存为/复制
- 还原为已保存

## 文件操作

- **importExport**：放置与使用应用程序本机不支持的格式导入和导出数据有关的命令。
- **newItem**：放置创建不同类型文档的命令。
- **printItem**：放置与打印应用程序内容相关的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/saveItem
crawled: 2025-12-03T06:23:39Z
---

# saveItem

**Type Property**

Placement for commands that save open documents and close windows.

## Declaration

```swift
static let saveItem: CommandGroupPlacement
```

## Discussion

By default, this group includes the following commands in macOS:

- Close
- Save
- Save As/Duplicate
- Revert to Saved

## File manipulation

- **importExport**: Placement for commands that relate to importing and exporting data using formats that the app doesn’t natively support.
- **newItem**: Placement for commands that create different kinds of documents.
- **printItem**: Placement for commands related to printing app content.

