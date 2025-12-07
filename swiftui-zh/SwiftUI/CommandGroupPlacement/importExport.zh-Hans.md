---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/importExport
抓取时间： 2025-12-03T06:23:36Z
---

# importExport

**类型属性**

用于放置与使用应用程序本机不支持的格式导入和导出数据有关的命令。

### 声明

```swift
static let importExport: CommandGroupPlacement
```

## 讨论

macOS 默认为空。

## 文件操作

- **newItem**：用于创建不同类型文件的命令的位置。
- **printItem**：放置与打印应用程序内容相关的命令。
- **saveItem**：保存打开的文档和关闭窗口的命令的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/importExport
crawled: 2025-12-03T06:23:36Z
---

# importExport

**Type Property**

Placement for commands that relate to importing and exporting data using formats that the app doesn’t natively support.

## Declaration

```swift
static let importExport: CommandGroupPlacement
```

## Discussion

Empty by default in macOS.

## File manipulation

- **newItem**: Placement for commands that create different kinds of documents.
- **printItem**: Placement for commands related to printing app content.
- **saveItem**: Placement for commands that save open documents and close windows.

