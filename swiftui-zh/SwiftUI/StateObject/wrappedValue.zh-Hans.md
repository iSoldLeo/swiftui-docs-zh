---

来源：https://developer.apple.com/documentation/SwiftUI/StateObject/wrappedValue
抓取时间：2025-12-02T21:00:20Z

---

# wrappedValue

**实例属性**

状态对象引用的底层值。

## 声明

```swift
@MainActor @preconcurrency var wrappedValue: ObjectType { get }
```

## 讨论

wrappedValue 属性提供对值数据的主要访问。但是，通常情况下您不会直接访问它。相反，当您引用使用 `@StateObject` 属性创建的变量时，SwiftUI 会为您访问此属性：

```swift
@StateObject private var contact = Contact()

var body: some View {
    Text(contact.name) // Reads name from contact's wrapped value.
}
```

当您更改 wrappedValue 时，您可以立即访问新值。但是，SwiftUI 会异步更新显示该值的视图，因此界面可能不会立即更新。

## 获取值

- **projectedValue**：状态对象的投影，用于创建与其属性的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/StateObject/wrappedValue
crawled: 2025-12-02T21:00:20Z
---

# wrappedValue

**Instance Property**

The underlying value referenced by the state object.

## Declaration

```swift
@MainActor @preconcurrency var wrappedValue: ObjectType { get }
```

## Discussion

The wrapped value property provides primary access to the value’s data. However, you don’t typically access it directly. Instead, SwiftUI accesses this property for you when you refer to the variable that you create with the `@StateObject` attribute:

```swift
@StateObject private var contact = Contact()

var body: some View {
    Text(contact.name) // Reads name from contact's wrapped value.
}
```

When you change a wrapped value, you can access the new value immediately. However, SwiftUI updates views that display the value asynchronously, so the interface might not update immediately.

## Getting the value

- **projectedValue**: A projection of the state object that creates bindings to its properties.

