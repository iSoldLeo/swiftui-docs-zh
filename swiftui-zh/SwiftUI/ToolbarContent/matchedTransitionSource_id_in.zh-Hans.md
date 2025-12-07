--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarContent/matchedTransitionSource(id:in:)

抓取时间：2025-12-01T10:52:19Z

---

# matchedTransitionSource(id:in:)

**实例方法**

将此工具栏内容标识为导航过渡（例如缩放过渡）的源。

## 声明

```swift
nonisolated func matchedTransitionSource(id: some Hashable, in namespace: Namespace.ID) -> some ToolbarContent

```

## 参数

- **id**：标识符，通常派生自工具栏内容所显示数据的标识符。

- **namespace**：定义 `id` 的命名空间。创建新的命名空间的方法是：向 [View](../View.zh-Hans.md) 或 `ToolbarContent` 类型添加一个 [Namespace](../Namespace.zh-Hans.md) 变量，并在该类型的主体方法中读取其值。

## 讨论

将此修饰符与 `View.navigationTransition(_:)` 结合使用，可为过渡效果提供源：

```swift
struct ContentView: View {
    @State private var isPresented = false
    @Namespace private var namespace

    var body: some View {
        NavigationStack {
            DetailView()
                .toolbar {
                    ToolbarItem(placement: .topBarTrailing) {
                        Button("Show Sheet", systemImage: "globe") {
                            isPresented = true
                        }
                    }
                    .matchedTransitionSource(
                        id: "world", in: namespace)
                }
                .sheet(isPresented: $isPresented) {
                    SheetView()
                        .navigationTransition(
                            .zoom(sourceID: "world", in: namespace))
                }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarContent/matchedTransitionSource(id:in:)
crawled: 2025-12-01T10:52:19Z
---

# matchedTransitionSource(id:in:)

**Instance Method**

Identifies this toolbar content as the source of a navigation transition, such as a zoom transition.

## Declaration

```swift
nonisolated func matchedTransitionSource(id: some Hashable, in namespace: Namespace.ID) -> some ToolbarContent

```

## Parameters

- **id**: The identifier, often derived from the identifier of the data being displayed by the toolbar content.
- **namespace**: The namespace in which defines the `id`. New namespaces are created by adding an [Namespace](../Namespace.zh-Hans.md) variable to a [View](../View.zh-Hans.md) or ``ToolbarContent` type and reading its value in the type’s body method.

## Discussion

Use this modifier in conjunction with `View.navigationTransition(_:)` to provide a source for the transition effect:

```swift
struct ContentView: View {
    @State private var isPresented = false
    @Namespace private var namespace

    var body: some View {
        NavigationStack {
            DetailView()
                .toolbar {
                    ToolbarItem(placement: .topBarTrailing) {
                        Button("Show Sheet", systemImage: "globe") {
                            isPresented = true
                        }
                    }
                    .matchedTransitionSource(
                        id: "world", in: namespace)
                }
                .sheet(isPresented: $isPresented) {
                    SheetView()
                        .navigationTransition(
                            .zoom(sourceID: "world", in: namespace))
                }
        }
    }
}
```

