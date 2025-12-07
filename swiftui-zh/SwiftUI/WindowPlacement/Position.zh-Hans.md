--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowPlacement/Position
抓取时间：2025-12-03T05:32:14Z

---

# WindowPlacement.Position

**Structure**

窗口位置的语义值或位置值。

## 声明

```swift
struct Position
```

## 类型属性

- **utilityPanel**：实用工具面板窗口的位置。

## 类型方法

- **above(_:)**：窗口相对于另一个窗口顶部边缘的位置。

- **below(_:)**：窗口相对于另一个窗口底部边缘的位置。

- **leading(_:)**：窗口相对于另一个窗口前边缘的位置。

- **replacing(_:)**：将窗口定位到与现有窗口相同的位置，同时隐藏旧窗口。

- **trailing(_:)**：窗口相对于另一个窗口后缘的位置。

## 符合以下规范

- Equatable


---
source: https://developer.apple.com/documentation/SwiftUI/WindowPlacement/Position
crawled: 2025-12-03T05:32:14Z
---

# WindowPlacement.Position

**Structure**

A semantic or positional value for the location of a window.

## Declaration

```swift
struct Position
```

## Type Properties

- **utilityPanel**: Utility panel window position.

## Type Methods

- **above(_:)**: Window position relative to the top edge of another window.
- **below(_:)**: Window position relative to the bottom edge of another window.
- **leading(_:)**: Window position relative to the leading edge of another window.
- **replacing(_:)**: Positions the window in the same spot as an existing window, hiding the old window in the process.
- **trailing(_:)**: Window position relative to the trailing edge of another window.

## Conforms To

- Equatable

