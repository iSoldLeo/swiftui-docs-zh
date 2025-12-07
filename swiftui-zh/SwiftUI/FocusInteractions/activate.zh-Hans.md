--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusInteractions/activate
抓取时间：2025-12-03T06:47:47Z

---

# activate

**类型属性**

该视图具有一个可通过焦点手势激活的主要操作。

## 声明

```swift
static let activate: FocusInteractions
```

## 讨论

在 macOS 和 iOS 上，仅当启用所有控制键盘导航时，才支持焦点驱动的激活交互。在 tvOS 和 watchOS 上，始终支持焦点驱动的激活交互。

## 创建交互类型

- **automatic**：该视图支持当前平台上交互式内容通常所需的所有焦点驱动交互。

- **edit**：该视图可捕获来自非空间来源（例如键盘或数码表冠）的输入。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusInteractions/activate
crawled: 2025-12-03T06:47:47Z
---

# activate

**Type Property**

The view has a primary action that can be activated via focus gestures.

## Declaration

```swift
static let activate: FocusInteractions
```

## Discussion

On macOS and iOS, focus-driven activation interactions are only possible when all-controls keyboard navigation is enabled. On tvOS and watchOS, focus-driven activation interactions are always possible.

## Creating the interaction types

- **automatic**: The view supports whatever focus-driven interactions are commonly expected for interactive content on the current platform.
- **edit**: The view captures input from non-spatial sources like a keyboard or Digital Crown.

