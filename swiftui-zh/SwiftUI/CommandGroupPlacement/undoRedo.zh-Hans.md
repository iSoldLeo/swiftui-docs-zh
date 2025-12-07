---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/undoRedo
抓取时间： 2025-12-03T06:23:42Z
---

# undoRedo

**类型属性**

用于控制撤消管理器的命令的位置。

## 声明

```swift
static let undoRedo: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包括以下命令：

- 撤销
- 重做

## 内容更新

- **pasteboard**：放置与剪贴板交互的命令，并操作应用程序视图层次结构中当前选中的内容。
- **textEditing**：用于放置操作和转换文本选区的命令。
- **textFormatting**：用于操作和变换应用于文本选区的样式的命令的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/undoRedo
crawled: 2025-12-03T06:23:42Z
---

# undoRedo

**Type Property**

Placement for commands that control the Undo Manager.

## Declaration

```swift
static let undoRedo: CommandGroupPlacement
```

## Discussion

By default, this group includes the following commands in macOS:

- Undo
- Redo

## Content updates

- **pasteboard**: Placement for commands that interact with the Clipboard and manipulate content that is currently selected in the app’s view hierarchy.
- **textEditing**: Placement for commands that manipulate and transform text selections.
- **textFormatting**: Placement for commands that manipulate and transform the styles applied to text selections.

