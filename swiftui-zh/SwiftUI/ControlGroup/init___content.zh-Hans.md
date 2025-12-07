---
来源： https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(_:content:)
抓取时间： 2025-12-01T10:29:39Z
---

# init(_:content:)

**Initializer**

用指定的内容创建一个新的控制组，该控制组的标签由字符串生成。

## 声明

```swift
nonisolated init<C, S>(_ title: S, @ViewBuilder content: () -> C) where Content == LabeledControlGroupContent<C, Text>, C : View, S : StringProtocol
```

## 参数

- **title**：描述组内容的字符串。

## 创建控制组

- **init(content:)**：创建一个带有指定子代的新控制组
- **init(content:label:)**：创建具有指定内容和标签的新控件组。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(_:content:)
crawled: 2025-12-01T10:29:39Z
---

# init(_:content:)

**Initializer**

Creates a new control group with the specified content that generates its label from a string.

## Declaration

```swift
nonisolated init<C, S>(_ title: S, @ViewBuilder content: () -> C) where Content == LabeledControlGroupContent<C, Text>, C : View, S : StringProtocol
```

## Parameters

- **title**: A string that describes the contents of the group.

## Creating a control group

- **init(content:)**: Creates a new ControlGroup with the specified children
- **init(content:label:)**: Creates a new control group with the specified content and a label.

