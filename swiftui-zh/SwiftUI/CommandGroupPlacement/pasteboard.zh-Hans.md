---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/pasteboard
抓取时间： 2025-12-03T06:23:39Z
---

# 粘贴板

**类型属性**

用于放置与剪贴板交互并操作应用程序视图层次结构中当前选中内容的命令。

### 声明

```swift
static let pasteboard: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包括以下命令：

- 剪切
- 复制
- 粘贴
- 粘贴并匹配样式
- 删除
- 全选

## 内容更新

- **textEditing**：放置操作和转换文本选区的命令。
- **textFormatting**：用于操作和变换应用于文本选区的样式的命令的位置。
- **undoRedo**：用于放置控制撤消管理器的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/pasteboard
crawled: 2025-12-03T06:23:39Z
---

# pasteboard

**Type Property**

Placement for commands that interact with the Clipboard and manipulate content that is currently selected in the app’s view hierarchy.

## Declaration

```swift
static let pasteboard: CommandGroupPlacement
```

## Discussion

By default, this group includes the following commands in macOS:

- Cut
- Copy
- Paste
- Paste and Match Style
- Delete
- Select All

## Content updates

- **textEditing**: Placement for commands that manipulate and transform text selections.
- **textFormatting**: Placement for commands that manipulate and transform the styles applied to text selections.
- **undoRedo**: Placement for commands that control the Undo Manager.

