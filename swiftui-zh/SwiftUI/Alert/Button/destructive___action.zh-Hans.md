---
来源：https://developer.apple.com/documentation/SwiftUI/Alert/Button/destructive(_:action:)
抓取时间： 2025-12-04T13:08:42Z
---

# destructive(_:action:)

**类型方法**

创建一个警告按钮，其样式表示破坏性操作。

## 声明

```swift
static func destructive(_ label: Text, action: (() -> Void)? = {}) -> Alert.Button
```

## 参数

- **label**：按钮上要显示的文本。
- **action**：用户点击或按下按钮时要执行的闭包。

## 返回值

表示破坏性操作的警报按钮。

## 获取按钮

- **default(_:action:)**：创建默认样式的警报按钮。
- **cancel(_:)**：创建表示取消的警报按钮，并带有系统提供的标签。
- **cancel(_:action:)**：创建表示取消的警报按钮，并带有自定义标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Alert/Button/destructive(_:action:)
crawled: 2025-12-04T13:08:42Z
---

# destructive(_:action:)

**Type Method**

Creates an alert button with a style that indicates a destructive action.

## Declaration

```swift
static func destructive(_ label: Text, action: (() -> Void)? = {}) -> Alert.Button
```

## Parameters

- **label**: The text to display on the button.
- **action**: A closure to execute when the user taps or presses the button.

## Return Value

An alert button that indicates a destructive action.

## Getting a button

- **default(_:action:)**: Creates an alert button with the default style.
- **cancel(_:)**: Creates an alert button that indicates cancellation, with a system-provided label.
- **cancel(_:action:)**: Creates an alert button that indicates cancellation, with a custom label.

