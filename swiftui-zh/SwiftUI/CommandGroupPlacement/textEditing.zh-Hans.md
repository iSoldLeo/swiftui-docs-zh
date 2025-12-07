---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/textEditing
抓取时间： 2025-12-03T06:23:40Z
---

# 文本编辑

**类型属性**

用于操作和转换文本选区的命令的位置。

## 声明

```swift
static let textEditing: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包括以下命令：

- 查找子菜单
- 拼写和语法子菜单
- 替换子菜单
- 转换子菜单
- 语音子菜单

## 内容更新

- **pasteboard**：用于放置与剪贴板交互的命令，以及操作当前在应用程序视图层级中选中的内容。
- **textFormatting**：用于放置操作和转换应用于文本选区的样式的命令。
- **undoRedo**：用于放置控制撤消管理器的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/textEditing
crawled: 2025-12-03T06:23:40Z
---

# textEditing

**Type Property**

Placement for commands that manipulate and transform text selections.

## Declaration

```swift
static let textEditing: CommandGroupPlacement
```

## Discussion

By default, this group includes the following commands in macOS:

- Find submenu
- Spelling and Grammar submenu
- Substitutions submenu
- Transformations submenu
- Speech submenu

## Content updates

- **pasteboard**: Placement for commands that interact with the Clipboard and manipulate content that is currently selected in the app’s view hierarchy.
- **textFormatting**: Placement for commands that manipulate and transform the styles applied to text selections.
- **undoRedo**: Placement for commands that control the Undo Manager.

