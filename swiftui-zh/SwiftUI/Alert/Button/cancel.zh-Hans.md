---
来源： https://developer.apple.com/documentation/SwiftUI/Alert/Button/cancel(_:)
抓取时间： 2025-12-04T13:08:41Z
---

# cancel(_:)

**类型方法**

创建一个表示取消的警报按钮，并带有系统提供的标签。

## 声明

```swift
static func cancel(_ action: (() -> Void)? = {}) -> Alert.Button
```

## 参数

- **action**：用户点击或按下按钮时要执行的闭包。

## 返回值

表示取消的警报按钮。

## 讨论

系统会自动为按钮标签选择适合当地语言的文本。

## 获取按钮

- **default(_:action:)**：创建一个具有默认样式的警报按钮。
- **cancel(_:action:)**：创建一个表示取消的警报按钮，并带有自定义标签。
- **destructive(_:action:)**：创建表示破坏性操作的警报按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/Alert/Button/cancel(_:)
crawled: 2025-12-04T13:08:41Z
---

# cancel(_:)

**Type Method**

Creates an alert button that indicates cancellation, with a system-provided label.

## Declaration

```swift
static func cancel(_ action: (() -> Void)? = {}) -> Alert.Button
```

## Parameters

- **action**: A closure to execute when the user taps or presses the button.

## Return Value

An alert button that indicates cancellation.

## Discussion

The system automatically chooses locale-appropriate text for the button’s label.

## Getting a button

- **default(_:action:)**: Creates an alert button with the default style.
- **cancel(_:action:)**: Creates an alert button that indicates cancellation, with a custom label.
- **destructive(_:action:)**: Creates an alert button with a style that indicates a destructive action.

