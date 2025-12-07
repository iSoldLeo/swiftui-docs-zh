--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusInteractions/edit

抓取时间：2025-12-03T06:47:48Z

---

# 编辑

**类型属性**

该视图可捕获来自非空间来源（例如键盘或数码表冠）的输入。

## 声明

```swift
static let edit: FocusInteractions
```

## 讨论

支持焦点驱动编辑交互的视图会在用户点击或单击，或发出焦点移动命令时获得焦点。

## 创建交互类型

- **automatic**：该视图支持当前平台上交互式内容通常所需的所有焦点驱动交互。

- **activate**：该视图具有可通过焦点手势激活的主要操作。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusInteractions/edit
crawled: 2025-12-03T06:47:48Z
---

# edit

**Type Property**

The view captures input from non-spatial sources like a keyboard or Digital Crown.

## Declaration

```swift
static let edit: FocusInteractions
```

## Discussion

Views that support focus-driven editing interactions become focused when the user taps or clicks on them, or when the user issues a focus movement command.

## Creating the interaction types

- **automatic**: The view supports whatever focus-driven interactions are commonly expected for interactive content on the current platform.
- **activate**: The view has a primary action that can be activated via focus gestures.

