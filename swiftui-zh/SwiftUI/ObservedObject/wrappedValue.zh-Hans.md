---
来源： https://developer.apple.com/documentation/SwiftUI/ObservedObject/wrappedValue
抓取时间： 2025-12-02T21:00:23Z
---

# wrappedValue

**实例属性**

观察对象引用的底层值。

## 声明

```swift
@MainActor @preconcurrency var wrappedValue: ObjectType
```

## 讨论

包装值属性提供了对观察对象数据的主要访问。但是，您通常不会通过名称来访问它。相反，当您引用使用`@ObservedObject` 属性创建的变量时，SwiftUI 会为您访问该属性。

```swift
struct MySubView: View {
    @ObservedObject var model: DataModel

    var body: some View {
        Text(model.name) // Reads name from model's wrapped value.
    }
}
```属性

更改封装值时，可以立即访问新值。但是，SwiftUI 会异步更新显示该值的视图，因此界面可能不会立即更新。

## 获取值

- **projectedValue**：观察对象的投影，可创建与其属性的绑定。
- **ObservedObject.Wrapper**：底层可观察对象的包装器，可为其属性创建绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/ObservedObject/wrappedValue
crawled: 2025-12-02T21:00:23Z
---

# wrappedValue

**Instance Property**

The underlying value that the observed object references.

## Declaration

```swift
@MainActor @preconcurrency var wrappedValue: ObjectType
```

## Discussion

The wrapped value property provides primary access to the observed object’s data. However, you don’t typically access it by name. Instead, SwiftUI accesses this property for you when you refer to the variable that you create with the `@ObservedObject` attribute.

```swift
struct MySubView: View {
    @ObservedObject var model: DataModel

    var body: some View {
        Text(model.name) // Reads name from model's wrapped value.
    }
}
```

When you change a wrapped value, you can access the new value immediately. However, SwiftUI updates views that display the value asynchronously, so the interface might not update immediately.

## Getting the value

- **projectedValue**: A projection of the observed object that creates bindings to its properties.
- **ObservedObject.Wrapper**: A wrapper of the underlying observable object that can create bindings to its properties.

