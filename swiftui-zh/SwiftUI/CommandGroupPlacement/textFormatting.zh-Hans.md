---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/textFormatting
抓取时间： 2025-12-03T06:23:41Z
---

# 文本格式

**类型属性**

用于操作和转换应用于文本选区的样式的命令的位置。

## 声明

```swift
static let textFormatting: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包括以下命令：

- 字体子菜单
- 文本子菜单

## 内容更新

- **pasteboard**：用于放置与剪贴板交互并操作当前在应用程序视图层次结构中所选内容的命令。
- **textEditing**：用于放置操作和转换文本选区的命令。
- **undoRedo**：用于放置控制撤消管理器的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/textFormatting
crawled: 2025-12-03T06:23:41Z
---

# textFormatting

**Type Property**

Placement for commands that manipulate and transform the styles applied to text selections.

## Declaration

```swift
static let textFormatting: CommandGroupPlacement
```

## Discussion

By default, this group includes the following commands in macOS:

- Font submenu
- Text submenu

## Content updates

- **pasteboard**: Placement for commands that interact with the Clipboard and manipulate content that is currently selected in the app’s view hierarchy.
- **textEditing**: Placement for commands that manipulate and transform text selections.
- **undoRedo**: Placement for commands that control the Undo Manager.

