--- 来源：https://developer.apple.com/documentation/SwiftUI/LayoutValueKey

抓取时间：2025-12-02T17:39:23Z

---

# LayoutValueKey

**Protocol**

用于访问布局容器子视图的布局值的键。

## 声明

```swift
protocol LayoutValueKey
```

## 概述

如果您通过定义符合 [Layout](Layout.zh-Hans.md) 协议的类型来创建自定义布局，您还可以创建自定义布局值，这些值可以设置在各个视图上，并且您的容器视图可以访问这些值来指导其布局行为。您的自定义值类似于您使用视图修饰符（例如 [layoutPriority(_:)](View/layoutPriority.zh-Hans.md) 和 [zIndex(_:)](View/zIndex.zh-Hans.md)）设置的内置布局值，但它们具有您定义的用途。

要创建自定义布局值，请定义一个符合 `LayoutValueKey` 协议的类型，并实现返回该属性默认值的必需属性。例如，您可以创建一个属性来定义视图的灵活性，该属性定义为可选的浮点数，默认值为 `nil`：

```swift
private struct Flexibility: LayoutValueKey {
    static let defaultValue: CGFloat? = nil
}
```

Swift 编译器会根据此定义推断此特定键的关联类型为可选的 [doc://com.apple.documentation/documentation/CoreFoundation/CGFloat-swift.struct]。

### 设置视图的值

要设置视图的值，请将 [layoutValue(key:value:)](View/layoutValue_key_value.zh-Hans.md) 视图修饰符添加到视图。为了方便您使用自定义值，您可以在 [View](View.zh-Hans.md) 协议的扩展中使用便捷修饰符来实现：

```swift
extension View {
    func layoutFlexibility(_ value: CGFloat?) -> some View {
        layoutValue(key: Flexibility.self, value: value)
    }
}
```

使用修饰符为任何需要非默认值的视图设置值：

```swift
BasicVStack {
    Text("One View")
    Text("Another View")
        .layoutFlexibility(3)
}
```

任何未显式设置值的视图都将使用默认值，例如上面的第一个 [Text](Text.zh-Hans.md) 视图。

### 在布局期间检索值

使用键作为子视图代理（[LayoutSubview](LayoutSubview.zh-Hans.md) 的实例）上的索引来访问自定义布局值，并使用该值来决定尺寸、位置或其他布局操作。例如，您可以在布局视图的 [sizeThatFits(_:)](LayoutSubview/sizeThatFits.zh-Hans.md) 方法中读取灵活性值，并据此调整尺寸计算：

```swift
extension BasicVStack {
    func sizeThatFits(
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout Void
    ) -> CGSize {

        // Map the flexibility property of each subview into an array.
        let flexibilities = subviews.map { subview in
            subview[Flexibility.self]
        }

        // Calculate and return the size of the layout container.
        // ...
    }
}
```

## 提供默认值

- **defaultValue**：键的默认值。

- **Value**：键值的类型。

## 将值与自定义布局中的视图关联

- **layoutValue(key:value:)**：将值与自定义布局属性关联。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutValueKey
crawled: 2025-12-02T17:39:23Z
---

# LayoutValueKey

**Protocol**

A key for accessing a layout value of a layout container’s subviews.

## Declaration

```swift
protocol LayoutValueKey
```

## Overview

If you create a custom layout by defining a type that conforms to the [Layout](Layout.zh-Hans.md) protocol, you can also create custom layout values that you set on individual views, and that your container view can access to guide its layout behavior. Your custom values resemble the built-in layout values that you set with view modifiers like [layoutPriority(_:)](View/layoutPriority.zh-Hans.md) and [zIndex(_:)](View/zIndex.zh-Hans.md), but have a purpose that you define.

To create a custom layout value, define a type that conforms to the `LayoutValueKey` protocol and implement the one required property that returns the default value of the property. For example, you can create a property that defines an amount of flexibility for a view, defined as an optional floating point number with a default value of `nil`:

```swift
private struct Flexibility: LayoutValueKey {
    static let defaultValue: CGFloat? = nil
}
```

The Swift compiler infers this particular key’s associated type as an optional [doc://com.apple.documentation/documentation/CoreFoundation/CGFloat-swift.struct] from this definition.

### Set a value on a view

Set the value on a view by adding the [layoutValue(key:value:)](View/layoutValue_key_value.zh-Hans.md) view modifier to the view. To make your custom value easier to work with, you can do this in a convenience modifier in an extension of the [View](View.zh-Hans.md) protocol:

```swift
extension View {
    func layoutFlexibility(_ value: CGFloat?) -> some View {
        layoutValue(key: Flexibility.self, value: value)
    }
}
```

Use your modifier to set the value on any views that need a nondefault value:

```swift
BasicVStack {
    Text("One View")
    Text("Another View")
        .layoutFlexibility(3)
}
```

Any view that you don’t explicitly set a value for uses the default value, as with the first [Text](Text.zh-Hans.md) view, above.

### Retrieve a value during layout

Access a custom layout value using the key as an index on subview’s proxy (an instance of [LayoutSubview](LayoutSubview.zh-Hans.md)) and use the value to make decisions about sizing, placement, or other layout operations. For example, you might read the flexibility value in your layout view’s [sizeThatFits(_:)](LayoutSubview/sizeThatFits.zh-Hans.md) method, and adjust your size calculations accordingly:

```swift
extension BasicVStack {
    func sizeThatFits(
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout Void
    ) -> CGSize {

        // Map the flexibility property of each subview into an array.
        let flexibilities = subviews.map { subview in
            subview[Flexibility.self]
        }

        // Calculate and return the size of the layout container.
        // ...
    }
}
```

## Providing a default value

- **defaultValue**: The default value of the key.
- **Value**: The type of the key’s value.

## Associating values with views in a custom layout

- **layoutValue(key:value:)**: Associates a value with a custom layout property.

