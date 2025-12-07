--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationDestination(for:destination:)

抓取时间：2025-12-02T16:24:12Z

---

# navigationDestination(for:destination:)

**实例方法**

将目标视图与导航堆栈中呈现的数据类型关联起来。

## 声明

```swift
nonisolated func navigationDestination<D, C>(for data: D.Type, @ViewBuilder destination: @escaping (D) -> C) -> some View where D : Hashable, C : View

```

## 参数

- **data**：此目标匹配的数据类型。

- **destination**：一个视图构建器，用于定义当堆栈的导航状态包含 `data` 类型的值时要显示的视图。闭包接受一个参数，即要呈现的数据值。

## 讨论

将此视图修饰符添加到 [NavigationStack](../NavigationStack.zh-Hans.md) 内的视图，以描述堆栈在呈现特定类型数据时显示的视图。使用 [NavigationLink](../NavigationLink.zh-Hans.md) 来呈现数据。例如，您可以为 [Color](../Color.zh-Hans.md) 实例的每次呈现显示一个 `ColorDetail` 视图：

```swift
NavigationStack {
    List {
        NavigationLink("Mint", value: Color.mint)
        NavigationLink("Pink", value: Color.pink)
        NavigationLink("Teal", value: Color.teal)
    }
    .navigationDestination(for: Color.self) { color in
        ColorDetail(color: color)
    }
    .navigationTitle("Colors")
}
```

如果堆栈需要呈现多种类型的数据，您可以向堆栈添加多个导航目标修饰符。

请勿将导航目标修饰符放在“延迟”容器（例如 [List](../List.zh-Hans.md) 或 [LazyVStack](../LazyVStack.zh-Hans.md)）内。这些容器仅在需要渲染到屏幕上时才会创建子视图。请将导航目标修饰符添加到这些容器之外，以便导航堆栈始终可以找到目标。

## 单列堆叠视图

- **NavigationStack**：显示根视图并允许您在根视图之上显示其他视图的视图。

- **NavigationPath**：表示导航堆栈内容的已去除类型信息的数据列表。

- **navigationDestination(isPresented:destination:)**：将目标视图与可用于将视图推送到 [NavigationStack](../NavigationStack.zh-Hans.md) 的绑定关联起来。

- **navigationDestination(item:destination:)**：将目标视图与绑定值关联起来，以便在导航堆栈或导航拆分视图中使用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationDestination(for:destination:)
crawled: 2025-12-02T16:24:12Z
---

# navigationDestination(for:destination:)

**Instance Method**

Associates a destination view with a presented data type for use within a navigation stack.

## Declaration

```swift
nonisolated func navigationDestination<D, C>(for data: D.Type, @ViewBuilder destination: @escaping (D) -> C) -> some View where D : Hashable, C : View

```

## Parameters

- **data**: The type of data that this destination matches.
- **destination**: A view builder that defines a view to display when the stack’s navigation state contains a value of type `data`. The closure takes one argument, which is the value of the data to present.

## Discussion

Add this view modifier to a view inside a [NavigationStack](../NavigationStack.zh-Hans.md) to describe the view that the stack displays when presenting a particular kind of data. Use a [NavigationLink](../NavigationLink.zh-Hans.md) to present the data. For example, you can present a `ColorDetail` view for each presentation of a [Color](../Color.zh-Hans.md) instance:

```swift
NavigationStack {
    List {
        NavigationLink("Mint", value: Color.mint)
        NavigationLink("Pink", value: Color.pink)
        NavigationLink("Teal", value: Color.teal)
    }
    .navigationDestination(for: Color.self) { color in
        ColorDetail(color: color)
    }
    .navigationTitle("Colors")
}
```

You can add more than one navigation destination modifier to the stack if it needs to present more than one kind of data.

Do not put a navigation destination modifier inside a “lazy” container, like [List](../List.zh-Hans.md) or [LazyVStack](../LazyVStack.zh-Hans.md). These containers create child views only when needed to render on screen. Add the navigation destination modifier outside these containers so that the navigation stack can always see the destination.

## Stacking views in one column

- **NavigationStack**: A view that displays a root view and enables you to present additional views over the root view.
- **NavigationPath**: A type-erased list of data representing the content of a navigation stack.
- **navigationDestination(isPresented:destination:)**: Associates a destination view with a binding that can be used to push the view onto a [NavigationStack](../NavigationStack.zh-Hans.md).
- **navigationDestination(item:destination:)**: Associates a destination view with a bound value for use within a navigation stack or navigation split view

