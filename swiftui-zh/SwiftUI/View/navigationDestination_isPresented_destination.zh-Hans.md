--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationDestination(isPresented:destination:)

抓取时间：2025-12-02T17:29:31Z

---

# navigationDestination(isPresented:destination:)

**实例方法**

将目标视图与一个绑定关联起来，该绑定可用于将视图推送到 [NavigationStack](../NavigationStack.zh-Hans.md)。

## 声明

```swift
nonisolated func navigationDestination<V>(isPresented: Binding<Bool>, @ViewBuilder destination: () -> V) -> some View where V : View

```

## 参数

- **isPresented**：一个绑定到布尔值的参数，指示 `destination` 当前是否呈现。

- **destination**：要呈现的视图。

## 讨论

通常，建议将路径绑定到导航堆栈以实现程序化导航。将此视图修饰符添加到 [NavigationStack](../NavigationStack.zh-Hans.md) 内的视图，即可通过编程方式将单个视图推送到堆栈中。这对于构建可以推送关联视图的组件非常有用。例如，您可以为特定颜色显示 `ColorDetail` 视图：

```swift
@State private var showDetails = false
var favoriteColor: Color

NavigationStack {
    VStack {
        Circle()
            .fill(favoriteColor)
        Button("Show details") {
            showDetails = true
        }
    }
    .navigationDestination(isPresented: $showDetails) {
        ColorDetail(color: favoriteColor)
    }
    .navigationTitle("My Favorite Color")
}
```

不要将导航目标修饰符放在“惰性”容器（例如 [List](../List.zh-Hans.md) 或 [LazyVStack](../LazyVStack.zh-Hans.md)）内。这些容器仅在需要渲染到屏幕上时才会创建子视图。请将导航目标修饰符添加到这些容器之外，以便导航堆栈始终可以找到目标位置。

## 单列堆叠视图

- **NavigationStack**：显示根视图并允许您在根视图之上显示其他视图的视图。

- **NavigationPath**：表示导航堆栈内容的已去除类型信息的数据列表。

- **navigationDestination(for:destination:)**：将目标视图与导航堆栈中显示的数据类型关联起来。

- **navigationDestination(item:destination:)**：将目标视图与绑定值关联起来，以便在导航堆栈或导航拆分视图中使用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationDestination(isPresented:destination:)
crawled: 2025-12-02T17:29:31Z
---

# navigationDestination(isPresented:destination:)

**Instance Method**

Associates a destination view with a binding that can be used to push the view onto a [NavigationStack](../NavigationStack.zh-Hans.md).

## Declaration

```swift
nonisolated func navigationDestination<V>(isPresented: Binding<Bool>, @ViewBuilder destination: () -> V) -> some View where V : View

```

## Parameters

- **isPresented**: A binding to a Boolean value that indicates whether `destination` is currently presented.
- **destination**: A view to present.

## Discussion

In general, favor binding a path to a navigation stack for programmatic navigation. Add this view modifier to a view inside a [NavigationStack](../NavigationStack.zh-Hans.md) to programmatically push a single view onto the stack. This is useful for building components that can push an associated view. For example, you can present a `ColorDetail` view for a particular color:

```swift
@State private var showDetails = false
var favoriteColor: Color

NavigationStack {
    VStack {
        Circle()
            .fill(favoriteColor)
        Button("Show details") {
            showDetails = true
        }
    }
    .navigationDestination(isPresented: $showDetails) {
        ColorDetail(color: favoriteColor)
    }
    .navigationTitle("My Favorite Color")
}
```

Do not put a navigation destination modifier inside a “lazy” container, like [List](../List.zh-Hans.md) or [LazyVStack](../LazyVStack.zh-Hans.md). These containers create child views only when needed to render on screen. Add the navigation destination modifier outside these containers so that the navigation stack can always see the destination.

## Stacking views in one column

- **NavigationStack**: A view that displays a root view and enables you to present additional views over the root view.
- **NavigationPath**: A type-erased list of data representing the content of a navigation stack.
- **navigationDestination(for:destination:)**: Associates a destination view with a presented data type for use within a navigation stack.
- **navigationDestination(item:destination:)**: Associates a destination view with a bound value for use within a navigation stack or navigation split view

