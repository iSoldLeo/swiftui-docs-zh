---
来源： https://developer.apple.com/documentation/SwiftUI/Color/accentColor
抓取时间：2025-12-03T05:39:50Z
---

# accentColor

**类型属性**

反映系统或应用程序重点颜色的颜色。

## 声明

```swift
static var accentColor: Color { get }
```

## 讨论

强调色是一种应用于视图和控件的宽泛主题色。您可以通过在应用程序的资产目录中指定强调色来在应用程序级别设置它。



以下代码使用应用程序的重点色渲染[Text](../Text.zh-Hans.md) 视图：

```swift
Text("Accent Color")
    .foregroundStyle(Color.accentColor)
```

## 获取语义颜色

- **primary**：主要内容使用的颜色。
- **secondary**：次要内容使用的颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/accentColor
crawled: 2025-12-03T05:39:50Z
---

# accentColor

**Type Property**

A color that reflects the accent color of the system or app.

## Declaration

```swift
static var accentColor: Color { get }
```

## Discussion

The accent color is a broad theme color applied to views and controls. You can set it at the application level by specifying an accent color in your app’s asset catalog.



The following code renders a [Text](../Text.zh-Hans.md) view using the app’s accent color:

```swift
Text("Accent Color")
    .foregroundStyle(Color.accentColor)
```

## Getting semantic colors

- **primary**: The color to use for primary content.
- **secondary**: The color to use for secondary content.

