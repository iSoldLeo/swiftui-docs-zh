--- 来源：https://developer.apple.com/documentation/SwiftUI/View/edgesIgnoringSafeArea(_:)

抓取时间：2025-12-03T05:35:42Z

---

# edgesIgnoringSafeArea(_:)

**实例方法**

更改视图的建议区域，使其扩展到屏幕安全区域之外。

## 声明

```swift
nonisolated func edgesIgnoringSafeArea(_ edges: Edge.Set) -> some View

```

## 参数

- **edges**：要扩展此视图请求大小的边缘集合。

## 返回值

一个视图，其可能沿着 `edges` 指定的边缘扩展到屏幕安全区域之外。

## 讨论

使用 `edgesIgnoringSafeArea(_:)` 可以更改此视图的提议区域，以便在提议被接受的情况下，此视图可以超出安全区域，延伸到屏幕指定边缘的边界。

例如，您可以提议文本视图忽略安全区域的顶部内边距：

```swift
VStack {
    Text("This text is outside of the top safe area.")
        .edgesIgnoringSafeArea([.top])
        .border(Color.purple)
    Text("This text is inside VStack.")
        .border(Color.yellow)
}
.border(Color.gray)
```

根据周围视图的层级结构，SwiftUI 可能不会响应 `edgesIgnoringSafeArea(_:)` 请求。例如，如果视图位于一个遵循屏幕安全区域的容器内，则可能会发生这种情况。在这种情况下，您可能需要将 `edgesIgnoringSafeArea(_:)` 应用于容器。

## 布局修饰符

- **frame()**：将此视图定位在一个不可见的框架内。

- **coordinateSpace(name:)**：为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和尺寸等维度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/edgesIgnoringSafeArea(_:)
crawled: 2025-12-03T05:35:42Z
---

# edgesIgnoringSafeArea(_:)

**Instance Method**

Changes the view’s proposed area to extend outside the screen’s safe areas.

## Declaration

```swift
nonisolated func edgesIgnoringSafeArea(_ edges: Edge.Set) -> some View

```

## Parameters

- **edges**: The set of the edges in which to expand the size requested for this view.

## Return Value

A view that may extend outside of the screen’s safe area on the edges specified by `edges`.

## Discussion

Use `edgesIgnoringSafeArea(_:)` to change the area proposed for this view so that — were the proposal accepted — this view could extend outside the safe area to the bounds of the screen for the specified edges.

For example, you can propose that a text view ignore the safe area’s top inset:

```swift
VStack {
    Text("This text is outside of the top safe area.")
        .edgesIgnoringSafeArea([.top])
        .border(Color.purple)
    Text("This text is inside VStack.")
        .border(Color.yellow)
}
.border(Color.gray)
```



Depending on the surrounding view hierarchy, SwiftUI may not honor an `edgesIgnoringSafeArea(_:)` request. This can happen, for example, if the view is inside a container that respects the screen’s safe area. In that case you may need to apply `edgesIgnoringSafeArea(_:)` to the container instead.

## Layout modifiers

- **frame()**: Positions this view within an invisible frame.
- **coordinateSpace(name:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.

