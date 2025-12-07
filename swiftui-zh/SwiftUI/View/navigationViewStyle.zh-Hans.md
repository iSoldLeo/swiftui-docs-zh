--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationViewStyle(_:)

抓取时间：2025-12-03T05:35:41Z

---

# navigationViewStyle(_:)

**实例方法**

设置此视图中导航视图的样式。

## 声明

```swift
nonisolated func navigationViewStyle<S>(_ style: S) -> some View where S : NavigationViewStyle

```

## 说明

使用此修饰符可以更改导航视图的外观和行为。例如，默认情况下，在更宽的环境中（例如横屏模式下的 iPad），导航视图会显示为多列：

您可以应用 [stack](../NavigationViewStyle/stack.zh-Hans.md) 样式来强制在这些环境中使用单列堆叠导航：

```swift
NavigationView {
    List {
        NavigationLink("Purple", destination: ColorDetail(color: .purple))
        NavigationLink("Pink", destination: ColorDetail(color: .pink))
        NavigationLink("Orange", destination: ColorDetail(color: .orange))
    }
    .navigationTitle("Colors")

    Text("Select a Color") // A placeholder to show before selection.
}
.navigationViewStyle(.stack)
```

## 导航视图样式

- **NavigationViewStyle**：导航视图外观和交互的规范。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationViewStyle(_:)
crawled: 2025-12-03T05:35:41Z
---

# navigationViewStyle(_:)

**Instance Method**

Sets the style for navigation views within this view.

## Declaration

```swift
nonisolated func navigationViewStyle<S>(_ style: S) -> some View where S : NavigationViewStyle

```

## Discussion

Use this modifier to change the appearance and behavior of navigation views. For example, by default, navigation views appear with multiple columns in wider environments, like iPad in landscape orientation:



You can apply the [stack](../NavigationViewStyle/stack.zh-Hans.md) style to force single-column stack navigation in these environments:

```swift
NavigationView {
    List {
        NavigationLink("Purple", destination: ColorDetail(color: .purple))
        NavigationLink("Pink", destination: ColorDetail(color: .pink))
        NavigationLink("Orange", destination: ColorDetail(color: .orange))
    }
    .navigationTitle("Colors")

    Text("Select a Color") // A placeholder to show before selection.
}
.navigationViewStyle(.stack)
```



## Styling navigation views

- **NavigationViewStyle**: A specification for the appearance and interaction of a navigation view.

