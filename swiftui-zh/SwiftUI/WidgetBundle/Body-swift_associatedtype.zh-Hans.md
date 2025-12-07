--- 来源：https://developer.apple.com/documentation/SwiftUI/WidgetBundle/Body-swift.associatedtype

抓取时间：2025-12-02T17:49:02Z

---

# 主体

**关联类型**

代表组件包内容的组件类型。

## 声明

```swift
associatedtype Body : Widget
```

## 讨论

当您支持多个组件时，Swift 会根据您对所需 [body-swift.property](body-swift_property.zh-Hans.md) 属性的实现来推断此类型。

## 实现组件包

- **body**：声明应用程序支持的组件组。

- **WidgetBundleBuilder**：用于构建组件包主体的自定义属性。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetBundle/Body-swift.associatedtype
crawled: 2025-12-02T17:49:02Z
---

# Body

**Associated Type**

The type of widget that represents the content of the bundle.

## Declaration

```swift
associatedtype Body : Widget
```

## Discussion

When you support more than one widget, Swift infers this type from your implementation of the required [body-swift.property](body-swift_property.zh-Hans.md) property.

## Implementing a widget bundle

- **body**: Declares the group of widgets that an app supports.
- **WidgetBundleBuilder**: A custom attribute that constructs a widget bundle’s body.

