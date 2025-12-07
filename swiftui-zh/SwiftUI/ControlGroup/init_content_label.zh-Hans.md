---
来源：https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(内容：标签：)
抓取时间： 2025-12-03T05:40:29Z
---

# init(content:label:)

**Initializer**

用指定的内容和标签创建一个新的控制组。

### 声明

```swift
nonisolated init<C, L>(@ViewBuilder content: () -> C, @ViewBuilder label: () -> L) where Content == LabeledControlGroupContent<C, L>, C : View, L : View
```

## 参数

- **content**：要显示的内容。
- **label**：描述分组目的的视图。

## 创建控制组

- **init(content:)**：创建一个带有指定子代的新控制组
- **init(_:content:)**：创建具有指定内容的新控件组，该控件组的标签由字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(content:label:)
crawled: 2025-12-03T05:40:29Z
---

# init(content:label:)

**Initializer**

Creates a new control group with the specified content and a label.

## Declaration

```swift
nonisolated init<C, L>(@ViewBuilder content: () -> C, @ViewBuilder label: () -> L) where Content == LabeledControlGroupContent<C, L>, C : View, L : View
```

## Parameters

- **content**: The content to display.
- **label**: A view that describes the purpose of the group.

## Creating a control group

- **init(content:)**: Creates a new ControlGroup with the specified children
- **init(_:content:)**: Creates a new control group with the specified content that generates its label from a string.

