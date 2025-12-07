--- 来源：https://developer.apple.com/documentation/SwiftUI/LayoutValueKey/defaultValue
抓取时间：2025-12-03T06:39:35Z

---

# defaultValue

**类型属性**

键的默认值。

## 声明

```swift
static var defaultValue: Self.Value { get }
```

## 讨论

为符合 [LayoutValueKey](../LayoutValueKey.zh-Hans.md) 协议的类型实现 `defaultValue` 属性。例如，您可以创建一个 `Flexibility` 布局值，其默认值为 `nil`：

```swift
private struct Flexibility: LayoutValueKey {
    static let defaultValue: CGFloat? = nil
}
```

您为 `defaultValue` 声明的类型设置布局键的 [Value](Value.zh-Hans.md) 关联类型。 Swift 编译器会将上述示例中键的关联类型推断为可选的 [doc://com.apple.documentation/documentation/CoreFoundation/CGFloat-swift.struct]。

任何未显式设置值的视图都将使用默认值。使用 [layoutValue(key:value:)](../View/layoutValue_key_value.zh-Hans.md) 修饰符可以覆盖视图的默认值。

## 提供默认值

- **Value**：键值的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutValueKey/defaultValue
crawled: 2025-12-03T06:39:35Z
---

# defaultValue

**Type Property**

The default value of the key.

## Declaration

```swift
static var defaultValue: Self.Value { get }
```

## Discussion

Implement the `defaultValue` property for a type that conforms to the [LayoutValueKey](../LayoutValueKey.zh-Hans.md) protocol. For example, you can create a `Flexibility` layout value that defaults to `nil`:

```swift
private struct Flexibility: LayoutValueKey {
    static let defaultValue: CGFloat? = nil
}
```

The type that you declare for the `defaultValue` sets the layout key’s [Value](Value.zh-Hans.md) associated type. The Swift compiler infers the key’s associated type in the above example as an optional [doc://com.apple.documentation/documentation/CoreFoundation/CGFloat-swift.struct].

Any view that you don’t explicitly set a value for uses the default value. Override the default value for a view using the [layoutValue(key:value:)](../View/layoutValue_key_value.zh-Hans.md) modifier.

## Providing a default value

- **Value**: The type of the key’s value.

