---
来源： https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(_:image:content:)
抓取时间： 2025-12-03T05:40:31Z
---

# init(_:image:content:)

**Initializer**

用指定的内容创建一个新的控制组，该控制组的标签由字符串和图像名称生成。

### 声明

```swift
nonisolated init<C, S>(_ title: S, image: ImageResource, @ViewBuilder content: () -> C) where Content == LabeledControlGroupContent<C, Label<Text, Image>>, C : View, S : StringProtocol
```

## 参数

- **title**：描述组内容的字符串。

## 创建带有图像的控制组

- **init(_:systemImage:content:)**：创建一个具有指定内容的新控制组，该组的标签由字符串和图像名称生成。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(_:image:content:)
crawled: 2025-12-03T05:40:31Z
---

# init(_:image:content:)

**Initializer**

Creates a new control group with the specified content that generates its label from a string and image name.

## Declaration

```swift
nonisolated init<C, S>(_ title: S, image: ImageResource, @ViewBuilder content: () -> C) where Content == LabeledControlGroupContent<C, Label<Text, Image>>, C : View, S : StringProtocol
```

## Parameters

- **title**: A string that describes the contents of the group.

## Creating a control group with an image

- **init(_:systemImage:content:)**: Creates a new control group with the specified content that generates its label from a string and image name.

