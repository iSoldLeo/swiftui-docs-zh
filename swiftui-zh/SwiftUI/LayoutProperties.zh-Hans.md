---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutProperties
抓取时间： 2025-12-02T17:39:20Z
---

# 布局属性

**Structure**

布局容器的特定布局属性。

## 声明

```swift
struct LayoutProperties
```

## 概览

该结构包含适用于布局容器的配置信息。例如，[stackOrientation](LayoutProperties/stackOrientation.zh-Hans.md) 值表示布局的主轴（如果有）。

您可以使用此类型的实例来描述自定义布局容器，它是一种符合[Layout](Layout.zh-Hans.md) 协议的类型。执行该协议的 [layoutProperties](Layout/layoutProperties.zh-Hans.md) 属性可返回一个实例。例如，您可以指示您的布局具有垂直堆栈方向：

```swift
extension BasicVStack {
    static var layoutProperties: LayoutProperties {
        var properties = LayoutProperties()
        properties.stackOrientation = .vertical
        return properties
    }
}
```

如果您没有在自定义布局中实现该属性，协议会提供一个默认实现，返回一个具有默认值的`LayoutProperties` 实例。

## 创建布局属性实例

- **init()**：创建一组默认属性。

## 获取布局属性

- **stackOrientation**：包含堆栈式容器的方向。

## 配置自定义布局

- **ProposedViewSize**：关于视图大小的建议。
- **ViewSpacing**：视图的几何间距偏好集合。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutProperties
crawled: 2025-12-02T17:39:20Z
---

# LayoutProperties

**Structure**

Layout-specific properties of a layout container.

## Declaration

```swift
struct LayoutProperties
```

## Overview

This structure contains configuration information that’s applicable to a layout container. For example, the [stackOrientation](LayoutProperties/stackOrientation.zh-Hans.md) value indicates the layout’s primary axis, if any.

You can use an instance of this type to characterize a custom layout container, which is a type that conforms to the [Layout](Layout.zh-Hans.md) protocol. Implement the protocol’s [layoutProperties](Layout/layoutProperties.zh-Hans.md) property to return an instance. For example, you can indicate that your layout has a vertical stack orientation:

```swift
extension BasicVStack {
    static var layoutProperties: LayoutProperties {
        var properties = LayoutProperties()
        properties.stackOrientation = .vertical
        return properties
    }
}
```

If you don’t implement the property in your custom layout, the protocol provides a default implementation that returns a `LayoutProperties` instance with default values.

## Creating a layout properties instance

- **init()**: Creates a default set of properties.

## Getting layout properties

- **stackOrientation**: The orientation of the containing stack-like container.

## Configuring a custom layout

- **ProposedViewSize**: A proposal for the size of a view.
- **ViewSpacing**: A collection of the geometric spacing preferences of a view.

## Conforms To

- Sendable
- SendableMetatype

