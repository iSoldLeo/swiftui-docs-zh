--- 来源：https://developer.apple.com/documentation/SwiftUI/View/layoutValue(key:value:)

抓取时间：2025-12-02T17:39:22Z

---

# layoutValue(key:value:)

**实例方法**

将值与自定义布局属性关联。

## 声明

```swift
nonisolated func layoutValue<K>(key: K.Type, value: K.Value) -> some View where K : LayoutValueKey

```

## 参数

- **key**：要为其设置值的键的类型。创建键时，请确保其类型符合 [LayoutValueKey](../LayoutValueKey.zh-Hans.md) 协议。

- **value**：要分配给此视图中键的值。该值必须与您在实现键的 [defaultValue](../LayoutValueKey/defaultValue.zh-Hans.md) 属性时为该键的关联值所定义的类型相同。

## 返回值

返回一个具有指定键的指定值的视图。

## 说明

使用此方法为使用 [LayoutValueKey](../LayoutValueKey.zh-Hans.md) 定义的自定义属性设置值。例如，如果您定义了一个 `Flexibility` 键，则可以使用该键的类型和值在 [Text](../Text.zh-Hans.md) 视图上设置该键：

```swift
Text("Another View")
    .layoutValue(key: Flexibility.self, value: 3)
```

为了方便起见，您可以在 [View](../View.zh-Hans.md) 的扩展中定义一个执行此操作的方法：

```swift
extension View {
    func layoutFlexibility(_ value: CGFloat?) -> some View {
        layoutValue(key: Flexibility.self, value: value)
    }
}
```

此方法使调用点更易于阅读：

```swift
Text("Another View")
    .layoutFlexibility(3)
```

如果您在符合 [Layout](../Layout.zh-Hans.md) 协议的类型中执行布局操作，则可以读取自定义布局类型的每个子视图的键关联值。可以通过为子视图的代理添加键值索引来实现。更多信息，请参阅 [LayoutValueKey](../LayoutValueKey.zh-Hans.md)。

## 将值与自定义布局中的视图关联

- **LayoutValueKey**：用于访问布局容器子视图的布局值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/View/layoutValue(key:value:)
crawled: 2025-12-02T17:39:22Z
---

# layoutValue(key:value:)

**Instance Method**

Associates a value with a custom layout property.

## Declaration

```swift
nonisolated func layoutValue<K>(key: K.Type, value: K.Value) -> some View where K : LayoutValueKey

```

## Parameters

- **key**: The type of the key that you want to set a value for. Create the key as a type that conforms to the [LayoutValueKey](../LayoutValueKey.zh-Hans.md) protocol.
- **value**: The value to assign to the key for this view. The value must be of the type that you establish for the key’s associated value when you implement the key’s [defaultValue](../LayoutValueKey/defaultValue.zh-Hans.md) property.

## Return Value

A view that has the specified value for the specified key.

## Discussion

Use this method to set a value for a custom property that you define with [LayoutValueKey](../LayoutValueKey.zh-Hans.md). For example, if you define a `Flexibility` key, you can set the key on a [Text](../Text.zh-Hans.md) view using the key’s type and a value:

```swift
Text("Another View")
    .layoutValue(key: Flexibility.self, value: 3)
```

For convenience, you might define a method that does this in an extension to [View](../View.zh-Hans.md):

```swift
extension View {
    func layoutFlexibility(_ value: CGFloat?) -> some View {
        layoutValue(key: Flexibility.self, value: value)
    }
}
```

This method makes the call site easier to read:

```swift
Text("Another View")
    .layoutFlexibility(3)
```

If you perform layout operations in a type that conforms to the [Layout](../Layout.zh-Hans.md) protocol, you can read the key’s associated value for each subview of your custom layout type. Do this by indexing the subview’s proxy with the key. For more information, see [LayoutValueKey](../LayoutValueKey.zh-Hans.md).

## Associating values with views in a custom layout

- **LayoutValueKey**: A key for accessing a layout value of a layout container’s subviews.

