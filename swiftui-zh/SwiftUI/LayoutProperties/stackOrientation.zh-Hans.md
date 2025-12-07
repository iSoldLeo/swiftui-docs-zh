---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutProperties/stackOrientation
抓取时间： 2025-12-03T06:39:25Z
---

# 堆栈方向

**实例属性**

堆栈类容器的方向。

## 声明

```swift
var stackOrientation: Axis?
```

## 讨论

某些视图会根据其所在容器的堆栈方向改变行为。例如，[Spacer](../Spacer.zh-Hans.md) 和 [Divider](../Divider.zh-Hans.md) 将其主轴与其容器的主轴对齐。

通过从[Layout](../Layout.zh-Hans.md) 类型的[layoutProperties](../Layout/layoutProperties.zh-Hans.md) 方法的实现中返回一个已配置的[LayoutProperties](../LayoutProperties.zh-Hans.md) 实例，为您的自定义布局容器设置方向。例如，您可以指出您的布局有一个 [vertical](../Axis/vertical.zh-Hans.md) 主轴：

```swift
extension BasicVStack {
    static var layoutProperties: LayoutProperties {
        var properties = LayoutProperties()
        properties.stackOrientation = .vertical
        return properties
    }
}
```

如果没有指定`nil` 的值，则默认值为`nil`，表示方向未知或布局不是一维的。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutProperties/stackOrientation
crawled: 2025-12-03T06:39:25Z
---

# stackOrientation

**Instance Property**

The orientation of the containing stack-like container.

## Declaration

```swift
var stackOrientation: Axis?
```

## Discussion

Certain views alter their behavior based on the stack orientation of the container that they appear in. For example, [Spacer](../Spacer.zh-Hans.md) and [Divider](../Divider.zh-Hans.md) align their major axis to match that of their container.

Set the orientation for your custom layout container by returning a configured [LayoutProperties](../LayoutProperties.zh-Hans.md) instance from your [Layout](../Layout.zh-Hans.md) type’s implementation of the [layoutProperties](../Layout/layoutProperties.zh-Hans.md) method. For example, you can indicate that your layout has a [vertical](../Axis/vertical.zh-Hans.md) major axis:

```swift
extension BasicVStack {
    static var layoutProperties: LayoutProperties {
        var properties = LayoutProperties()
        properties.stackOrientation = .vertical
        return properties
    }
}
```

A value of `nil`, which is the default when you don’t specify a value, indicates an unknown orientation, or that a layout isn’t one-dimensional.

