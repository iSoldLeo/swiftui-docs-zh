---
来源：https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(_:systemImage:content:)
抓取时间： 2025-12-01T10:29:40Z


# init(_:systemImage:content:)

**Initializer**

用指定的内容创建一个新的控制组，该控制组的标签由字符串和图像名称生成。

### 声明

```swift
nonisolated init<C, S>(_ title: S, systemImage: String, @ViewBuilder content: () -> C) where Content == LabeledControlGroupContent<C, Label<Text, Image>>, C : View, S : StringProtocol
```

## 参数

- **title**：描述组内容的字符串。
- **systemImage**：要查找的图像资源的名称。

## 创建带有图像的控制组

- **init(_:image:content:)**：用指定的内容创建一个新的控制组，该控制组的标签由字符串和图像名称生成。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(_:systemImage:content:)
crawled: 2025-12-01T10:29:40Z
---

# init(_:systemImage:content:)

**Initializer**

Creates a new control group with the specified content that generates its label from a string and image name.

## Declaration

```swift
nonisolated init<C, S>(_ title: S, systemImage: String, @ViewBuilder content: () -> C) where Content == LabeledControlGroupContent<C, Label<Text, Image>>, C : View, S : StringProtocol
```

## Parameters

- **title**: A string that describes the contents of the group.
- **systemImage**: The name of the image resource to lookup.

## Creating a control group with an image

- **init(_:image:content:)**: Creates a new control group with the specified content that generates its label from a string and image name.

