--- 来源：https://developer.apple.com/documentation/SwiftUI/Bindable/init(_:)

抓取时间：2025-12-03T06:06:34Z

---

# init(_:)

**Initializer**

从可观察对象创建可绑定对象。

## 声明

```swift
init(_ wrappedValue: Value)
```

## 讨论

此初始化器等效于 [init(wrappedValue:)](init_wrappedValue.zh-Hans.md)，但在创建嵌套在其他表达式中的可绑定对象时更加简洁。例如，您可以使用初始化器在声明视图的代码中内联创建一个可绑定对象，该视图接受一个绑定作为参数：

```swift
struct TitleEditView: View {
    @Environment(Book.self) private var book

    var body: some View {
        TextField("Title", text: Bindable(book).title)
    }
}
```

## 创建可绑定值

- **init(wrappedValue:)**：从可观察对象创建可绑定对象。

- **init(projectedValue:)**：从另一个可绑定对象的值创建可绑定对象。


---
source: https://developer.apple.com/documentation/SwiftUI/Bindable/init(_:)
crawled: 2025-12-03T06:06:34Z
---

# init(_:)

**Initializer**

Creates a bindable object from an observable object.

## Declaration

```swift
init(_ wrappedValue: Value)
```

## Discussion

This initializer is equivalent to [init(wrappedValue:)](init_wrappedValue.zh-Hans.md), but is more succinct when when creating bindable objects nested within other expressions. For example, you can use the initializer to create a bindable object inline with code that declares a view that takes a binding as a parameter:

```swift
struct TitleEditView: View {
    @Environment(Book.self) private var book

    var body: some View {
        TextField("Title", text: Bindable(book).title)
    }
}
```

## Creating a bindable value

- **init(wrappedValue:)**: Creates a bindable object from an observable object.
- **init(projectedValue:)**: Creates a bindable from the value of another bindable.

