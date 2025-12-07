---
来源：https://developer.apple.com/documentation/SwiftUI/Alert/Button/default(_:action:)
抓取时间： 2025-12-04T13:08:40Z
---

# default(_:action:)

**类型方法**

以默认样式创建警报按钮。

## 声明

```swift
static func `default`(_ label: Text, action: (() -> Void)? = {}) -> Alert.Button
```

## 参数

- **label**：按钮上要显示的文本。
- **action**：用户点击或按下按钮时要执行的闭包。

## 返回值

默认样式的警报按钮。

## 获取按钮

- **cancel(_:)**：创建一个表示取消的警报按钮，并带有系统提供的标签。
- **cancel(_:action:)**：创建表示取消的警报按钮，并带有自定义标签。
- **destructive(_:action:)**：创建表示破坏性操作的警报按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/Alert/Button/default(_:action:)
crawled: 2025-12-04T13:08:40Z
---

# default(_:action:)

**Type Method**

Creates an alert button with the default style.

## Declaration

```swift
static func `default`(_ label: Text, action: (() -> Void)? = {}) -> Alert.Button
```

## Parameters

- **label**: The text to display on the button.
- **action**: A closure to execute when the user taps or presses the button.

## Return Value

An alert button with the default style.

## Getting a button

- **cancel(_:)**: Creates an alert button that indicates cancellation, with a system-provided label.
- **cancel(_:action:)**: Creates an alert button that indicates cancellation, with a custom label.
- **destructive(_:action:)**: Creates an alert button with a style that indicates a destructive action.

