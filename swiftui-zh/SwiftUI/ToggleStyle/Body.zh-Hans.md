---
来源： https://developer.apple.com/documentation/SwiftUI/ToggleStyle/Body
抓取时间： 2025-12-03T06:09:51Z
---

# 正文

**相关类型**

表示切换器的外观和交互的视图。

## 声明

```swift
associatedtype Body : View
```

## 讨论

SwiftUI 会根据您在实现[View](../View.zh-Hans.md) 方法时返回的[makeBody(configuration:)](makeBody_configuration.zh-Hans.md) 实例自动推断出此类型。

## 创建自定义切换样式

- **makeBody(configuration:)**：创建表示切换主体的视图。
- **ToggleStyleConfiguration**：切换实例的属性。
- **ToggleStyle.Configuration**：切换实例的属性：切换实例的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyle/Body
crawled: 2025-12-03T06:09:51Z
---

# Body

**Associated Type**

A view that represents the appearance and interaction of a toggle.

## Declaration

```swift
associatedtype Body : View
```

## Discussion

SwiftUI infers this type automatically based on the [View](../View.zh-Hans.md) instance that you return from your implementation of the [makeBody(configuration:)](makeBody_configuration.zh-Hans.md) method.

## Creating custom toggle styles

- **makeBody(configuration:)**: Creates a view that represents the body of a toggle.
- **ToggleStyleConfiguration**: The properties of a toggle instance.
- **ToggleStyle.Configuration**: The properties of a toggle instance.

