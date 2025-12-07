---
来源： https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(内容：)
抓取时间： 2025-12-03T05:40:29Z
---

# init(content:)

**Initializer**

创建带有指定子代的新 ControlGroup

## 声明

```swift
init(@ViewBuilder content: () -> Content)
```

## 参数

- **content**：要显示的子代

## 创建控制组

- **init(content:label:)**：用指定的内容和标签创建一个新的控制组。
- **init(_:content:)**：创建具有指定内容的新控制组，该控制组的标签由字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(content:)
crawled: 2025-12-03T05:40:29Z
---

# init(content:)

**Initializer**

Creates a new ControlGroup with the specified children

## Declaration

```swift
init(@ViewBuilder content: () -> Content)
```

## Parameters

- **content**: The children to display

## Creating a control group

- **init(content:label:)**: Creates a new control group with the specified content and a label.
- **init(_:content:)**: Creates a new control group with the specified content that generates its label from a string.

