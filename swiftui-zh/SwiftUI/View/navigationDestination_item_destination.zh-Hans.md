--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationDestination(item:destination:)

抓取时间：2025-11-30T21:14:36Z

---

# navigationDestination(item:destination:)

**实例方法**

将目标视图与绑定值关联，以便在导航堆栈或导航拆分视图中使用

## 声明

```swift
nonisolated func navigationDestination<D, C>(item: Binding<Optional<D>>, @ViewBuilder destination: @escaping (D) -> C) -> some View where D : Hashable, C : View

```

## 参数

- **item**：指向当前显示数据的绑定，如果当前未显示任何内容，则为 `nil`。

- **destination**：定义当 `item` 不等于 `nil` 时要显示的视图的视图构建器。

## 讨论

将此视图修饰符添加到 [NavigationStack](../NavigationStack.zh-Hans.md) 或 [NavigationSplitView](../NavigationSplitView.zh-Hans.md) 内的视图，以描述堆栈在呈现特定类型数据时显示的视图。通过编程方式更新绑定以显示或移除视图。例如，您可以替换导航拆分视图详细信息列中显示的视图：

```swift
@State private var colorShown: Color?

NavigationSplitView {
    List {
        Button("Mint") { colorShown = .mint }
        Button("Pink") { colorShown = .pink }
        Button("Teal") { colorShown = .teal }
    }
    .navigationDestination(item: $colorShown) { color in
        ColorDetail(color: color)
    }
} detail: {
    Text("Select a color")
}
```

当应用用户点击“薄荷绿”按钮时，详细信息中会显示薄荷绿，并且 `colorShown` 的值会变为 `Color.mint`。您可以通过将 `colorShown` 设置回 `nil` 来重置导航拆分视图，以显示“选择颜色”消息。

如果需要呈现多种类型的数据，您可以向堆栈添加多个导航目标修饰符。

请勿将导航目标修饰符放在“延迟”容器（例如 [List](../List.zh-Hans.md) 或 [LazyVStack](../LazyVStack.zh-Hans.md)）内。这些容器仅在需要渲染到屏幕上时才会创建子视图。请将导航目标修饰符添加到这些容器之外，以便导航拆分视图始终能够看到目标位置。

## 单列堆叠视图

- **NavigationStack**：显示根视图并允许您在根视图之上显示其他视图的视图。

- **NavigationPath**：表示导航堆栈内容的已擦除类型的数据列表。

- **navigationDestination(for:destination:)**：将目标视图与在导航堆栈中使用的数据类型关联起来。

- **navigationDestination(isPresented:destination:)**：将目标视图与可用于将视图推送到 [NavigationStack](../NavigationStack.zh-Hans.md) 的绑定关联起来。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationDestination(item:destination:)
crawled: 2025-11-30T21:14:36Z
---

# navigationDestination(item:destination:)

**Instance Method**

Associates a destination view with a bound value for use within a navigation stack or navigation split view

## Declaration

```swift
nonisolated func navigationDestination<D, C>(item: Binding<Optional<D>>, @ViewBuilder destination: @escaping (D) -> C) -> some View where D : Hashable, C : View

```

## Parameters

- **item**: A binding to the data presented, or `nil` if nothing is currently presented.
- **destination**: A view builder that defines a view to display when `item` is not `nil`.

## Discussion

Add this view modifier to a view inside a [NavigationStack](../NavigationStack.zh-Hans.md) or [NavigationSplitView](../NavigationSplitView.zh-Hans.md) to describe the view that the stack displays when presenting a particular kind of data. Programmatically update the binding to display or remove the view. For example, you can replace the view showing in the detail column of a navigation split view:

```swift
@State private var colorShown: Color?

NavigationSplitView {
    List {
        Button("Mint") { colorShown = .mint }
        Button("Pink") { colorShown = .pink }
        Button("Teal") { colorShown = .teal }
    }
    .navigationDestination(item: $colorShown) { color in
        ColorDetail(color: color)
    }
} detail: {
    Text("Select a color")
}
```

When the person using the app taps on the Mint button, the mint color shows in the detail and `colorShown` gets the value `Color.mint`. You can reset the navigation split view to show the message “Select a color” by setting `colorShown` back to `nil`.

You can add more than one navigation destination modifier to the stack if it needs to present more than one kind of data.

Do not put a navigation destination modifier inside a “lazy” container, like [List](../List.zh-Hans.md) or [LazyVStack](../LazyVStack.zh-Hans.md). These containers create child views only when needed to render on screen. Add the navigation destination modifier outside these containers so that the navigation split view can always see the destination.

## Stacking views in one column

- **NavigationStack**: A view that displays a root view and enables you to present additional views over the root view.
- **NavigationPath**: A type-erased list of data representing the content of a navigation stack.
- **navigationDestination(for:destination:)**: Associates a destination view with a presented data type for use within a navigation stack.
- **navigationDestination(isPresented:destination:)**: Associates a destination view with a binding that can be used to push the view onto a [NavigationStack](../NavigationStack.zh-Hans.md).

