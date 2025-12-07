---
来源： https://developer.apple.com/documentation/SwiftUI/SceneStorage/init(wrappedValue:_:)
抓取时间： 2025-12-01T00:44:28Z
---

# init(wrappedValue:_:)

**Initializer**

创建一个可以保存和恢复整数的属性，并将其转换为`RawRepresentable` 数据类型。

### 声明

```swift
init(wrappedValue: Value, _ key: String) where Value : RawRepresentable, Value.RawValue == Int
```

## 参数

- **wrappedValue**：如果给定键没有整数值，则使用默认值。
- **key**：用于保存和恢复值的键。

## 讨论

常见的用法是枚举：

```swift
enum MyEnum: Int {
    case a
    case b
    case c
}
struct MyView: View {
    @SceneStorage("MyEnumValue") private var value = MyEnum.a
    var body: some View { ... }
}
```

## 存储一个值

- **init(_:)**：创建一个可以保存和恢复可选布尔值的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/SceneStorage/init(wrappedValue:_:)
crawled: 2025-12-01T00:44:28Z
---

# init(wrappedValue:_:)

**Initializer**

Creates a property that can save and restore an integer, transforming it to a `RawRepresentable` data type.

## Declaration

```swift
init(wrappedValue: Value, _ key: String) where Value : RawRepresentable, Value.RawValue == Int
```

## Parameters

- **wrappedValue**: The default value if an integer value is not available for the given key.
- **key**: A key used to save and restore the value.

## Discussion

A common usage is with enumerations:

```swift
enum MyEnum: Int {
    case a
    case b
    case c
}
struct MyView: View {
    @SceneStorage("MyEnumValue") private var value = MyEnum.a
    var body: some View { ... }
}
```

## Storing a value

- **init(_:)**: Creates a property that can save and restore an Optional boolean.

