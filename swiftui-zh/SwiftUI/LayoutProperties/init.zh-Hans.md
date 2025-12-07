---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutProperties/init()
抓取时间： 2025-12-01T11:28:41Z
---

# init()

**Initializer**

创建一组默认属性。

## 声明

```swift
init()
```

## 讨论

使用布局属性实例可以提供有关符合[Layout](../Layout.zh-Hans.md) 协议的类型的信息。例如，你可以在布局对 [layoutProperties](../Layout/layoutProperties.zh-Hans.md) 方法的实现中创建一个布局属性实例，并用它来表示布局具有 [vertical](../Axis/vertical.zh-Hans.md) 方向：

```swift
extension BasicVStack {
    static var layoutProperties: LayoutProperties {
        var properties = LayoutProperties()
        properties.stackOrientation = .vertical
        return properties
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutProperties/init()
crawled: 2025-12-01T11:28:41Z
---

# init()

**Initializer**

Creates a default set of properties.

## Declaration

```swift
init()
```

## Discussion

Use a layout properties instance to provide information about a type that conforms to the [Layout](../Layout.zh-Hans.md) protocol. For example, you can create a layout properties instance in your layout’s implementation of the [layoutProperties](../Layout/layoutProperties.zh-Hans.md) method, and use it to indicate that the layout has a [vertical](../Axis/vertical.zh-Hans.md) orientation:

```swift
extension BasicVStack {
    static var layoutProperties: LayoutProperties {
        var properties = LayoutProperties()
        properties.stackOrientation = .vertical
        return properties
    }
}
```

