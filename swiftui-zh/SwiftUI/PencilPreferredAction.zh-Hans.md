---
来源： https://developer.apple.com/documentation/SwiftUI/PencilPreferredAction
抓取时间： 2025-12-02T17:41:07Z
---

# PencilPreferredAction

**Structure**

用户双击 Apple Pencil 后喜欢执行的操作。

## 声明

```swift
struct PencilPreferredAction
```

## 获取首选操作

- **ignore**：什么也不做的操作。
- **showColorPalette**：切换显示调色板的操作。
- **showInkAttributes**：用于切换显示当前工具的墨水属性的操作。
- **switchEraser**：在当前工具和橡皮之间切换的操作。
- **switchPrevious**：在当前工具和上次使用的工具之间切换的操作。

### 类型属性

- **runSystemShortcut**：运行系统快捷方式的操作。
- **showContextualPalette**：切换显示上下文调板的操作，如果上下文调板不可用，则切换显示撤消/重做面板的操作。

## 识别 Apple Pencil 手势

- **onPencilDoubleTap(perform:)**：在用户双击 Apple Pencil 后添加要执行的操作。
- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 时要执行的操作。
- **preferredPencilDoubleTapAction**：用户喜欢在双击 Apple Pencil 后执行的操作，如在设置 app 中所选。
- **preferredPencilSqueezeAction**：用户在设置 app 中选择的挤压 Apple Pencil 时喜欢执行的操作。
- **PencilDoubleTapGestureValue**：描述 Apple Pencil 双击手势的值。
- **PencilSqueezeGestureValue**：描述 Apple Pencil 双击手势的值：描述 Apple Pencil 挤压手势的值。
- **PencilSqueezeGesturePhase**：描述 Apple Pencil 挤压手势的相位和值。
- **PencilHoverPose**：描述 Apple Pencil 在视图边界上方区域悬停的位置和距离的值。

## 符合

- 等价
- 哈希值


---
source: https://developer.apple.com/documentation/SwiftUI/PencilPreferredAction
crawled: 2025-12-02T17:41:07Z
---

# PencilPreferredAction

**Structure**

An action that the user prefers to perform after double-tapping their Apple Pencil.

## Declaration

```swift
struct PencilPreferredAction
```

## Getting the preffered actions

- **ignore**: An action that does nothing.
- **showColorPalette**: An action that toggles the display of the color palette.
- **showInkAttributes**: An action that toggles the display of the current tool’s ink attributes.
- **switchEraser**: An action that switches between the current tool and the eraser.
- **switchPrevious**: An action that switches between the current tool and the last used tool.

## Type Properties

- **runSystemShortcut**: An action that runs a system shortcut.
- **showContextualPalette**: An action that toggles the display of the contextual palette, or the undo/redo panel if contextual palette is not available.

## Recognizing Apple Pencil gestures

- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.
- **PencilDoubleTapGestureValue**: Describes the value of an Apple Pencil double-tap gesture.
- **PencilSqueezeGestureValue**: Describes the value of an Apple Pencil squeeze gesture.
- **PencilSqueezeGesturePhase**: Describes the phase and value of an Apple Pencil squeeze gesture.
- **PencilHoverPose**: A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

## Conforms To

- Equatable
- Hashable

