---
来源： https://developer.apple.com/documentation/SwiftUI/ToggleStyle/Configuration
抓取时间： 2025-12-03T06:09:50Z
---

# ToggleStyle.Configuration

**类型别名**

切换实例的属性。

## 声明

```swift
typealias Configuration = ToggleStyleConfiguration
```

## 讨论

当您在自定义的切换样式实现中实现所需的[makeBody(configuration:)](makeBody_configuration.zh-Hans.md)方法时，您将收到该类型的`configuration`参数，它是[ToggleStyleConfiguration](../ToggleStyleConfiguration.zh-Hans.md)类型的别名。

## 创建自定义切换样式

- **makeBody(configuration:)**：创建表示切换主体的视图。
- **ToggleStyleConfiguration**：切换实例的属性。
- **Body**：切换实例的属性：表示切换开关的外观和交互的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyle/Configuration
crawled: 2025-12-03T06:09:50Z
---

# ToggleStyle.Configuration

**Type Alias**

The properties of a toggle instance.

## Declaration

```swift
typealias Configuration = ToggleStyleConfiguration
```

## Discussion

You receive a `configuration` parameter of this type — which is an alias for the [ToggleStyleConfiguration](../ToggleStyleConfiguration.zh-Hans.md) type — when you implement the required [makeBody(configuration:)](makeBody_configuration.zh-Hans.md) method in a custom toggle style implementation.

## Creating custom toggle styles

- **makeBody(configuration:)**: Creates a view that represents the body of a toggle.
- **ToggleStyleConfiguration**: The properties of a toggle instance.
- **Body**: A view that represents the appearance and interaction of a toggle.

