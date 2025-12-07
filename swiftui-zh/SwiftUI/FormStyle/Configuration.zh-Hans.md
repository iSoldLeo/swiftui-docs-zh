---
来源： https://developer.apple.com/documentation/SwiftUI/FormStyle/Configuration
抓取时间： 2025-12-03T06:11:39Z
---

# FormStyle.Configuration

**类型别名**

表单实例的属性。

## 声明

```swift
typealias Configuration = FormStyleConfiguration
```

## 讨论

当您在自定义表单样式实现中实现所需的[makeBody(configuration:)](makeBody_configuration.zh-Hans.md)方法时，您将收到该类型的`configuration`参数，它是[FormStyleConfiguration](../FormStyleConfiguration.zh-Hans.md)类型的别名。

## 创建自定义表单样式

- **makeBody(configuration:)**：创建表示表单主体的视图。
- **Body**：表示表单的外观和交互的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/FormStyle/Configuration
crawled: 2025-12-03T06:11:39Z
---

# FormStyle.Configuration

**Type Alias**

The properties of a form instance.

## Declaration

```swift
typealias Configuration = FormStyleConfiguration
```

## Discussion

You receive a `configuration` parameter of this type — which is an alias for the [FormStyleConfiguration](../FormStyleConfiguration.zh-Hans.md) type — when you implement the required [makeBody(configuration:)](makeBody_configuration.zh-Hans.md) method in a custom form style implementation.

## Creating custom form styles

- **makeBody(configuration:)**: Creates a view that represents the body of a form.
- **Body**: A view that represents the appearance and interaction of a form.

