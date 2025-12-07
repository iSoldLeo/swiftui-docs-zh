--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onGeometryChange(for:of:action:)

抓取时间：2025-11-30T21:22:53Z

---

# onGeometryChange(for:of:action:)

**实例方法**

添加一个操作，当由几何代理创建的值发生更改时执行。

## 声明

```swift
@preconcurrency nonisolated func onGeometryChange<T>(for type: T.Type, of transform: @escaping (GeometryProxy) -> T, action: @escaping (T) -> Void) -> some View where T : Equatable, T : Sendable

```

## 参数

- **type**：由 [GeometryProxy](../GeometryProxy.zh-Hans.md) 转换而来的值的类型。

- **transform**：一个闭包，用于将 [GeometryProxy](../GeometryProxy.zh-Hans.md) 转换为您的类型。

- **action**：一个闭包，用于在转换后的数据发生更改时运行。

## 讨论

视图的几何形状可能会频繁变化，尤其是在视图包含在滚动视图 [ScrollView](../ScrollView.zh-Hans.md) 中且该滚动视图正在滚动时。

您应该避免在滚动几何形状发生变化时更新应用程序的大部分内容。为了帮助您做到这一点，您可以为此修饰符提供两个闭包：

- transform：将 [GeometryProxy](../GeometryProxy.zh-Hans.md) 的值转换为您自己的数据类型。

- action：提供您在 `of` 中创建的数据类型，并在数据类型发生变化时调用。

例如，您可以使用此修饰符来了解视图在屏幕上的可见范围。在以下示例中，您转换为的数据类型是 `Bool`，并且当 `Bool` 发生变化时，将调用 action。

```swift
ScrollView(.horizontal) {
    LazyHStack {
         ForEach(videos) { video in
             VideoView(video)
         }
     }
 }

struct VideoView: View {
    var video: VideoModel

    var body: some View {
        VideoPlayer(video)
            .onGeometryChange(for: Bool.self) { proxy in
                let frame = proxy.frame(in: .scrollView)
                let bounds = proxy.bounds(of: .scrollView) ?? .zero
                let intersection = frame.intersection(
                    CGRect(origin: .zero, size: bounds.size))
                let visibleHeight = intersection.size.height
                return (visibleHeight / frame.size.height) > 0.75
            } action: { isVisible in
                video.updateAutoplayingState(
                    isVisible: isVisible)
            }
    }
}
```

要轻松响应滚动视图的几何体变化，请参阅 [onScrollGeometryChange(for:of:action:)](onScrollGeometryChange_for_of_action.zh-Hans.md) 修改器。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onGeometryChange(for:of:action:)
crawled: 2025-11-30T21:22:53Z
---

# onGeometryChange(for:of:action:)

**Instance Method**

Adds an action to be performed when a value, created from a geometry proxy, changes.

## Declaration

```swift
@preconcurrency nonisolated func onGeometryChange<T>(for type: T.Type, of transform: @escaping (GeometryProxy) -> T, action: @escaping (T) -> Void) -> some View where T : Equatable, T : Sendable

```

## Parameters

- **type**: The type of value transformed from a [GeometryProxy](../GeometryProxy.zh-Hans.md).
- **transform**: A closure that transforms a [GeometryProxy](../GeometryProxy.zh-Hans.md) to your type.
- **action**: A closure to run when the transformed data changes.

## Discussion

The geometry of a view can change frequently, especially if the view is contained within a [ScrollView](../ScrollView.zh-Hans.md) and that scroll view is scrolling.

You should avoid updating large parts of your app whenever the scroll geometry changes. To aid in this, you provide two closures to this modifier:

- transform: This converts a value of [GeometryProxy](../GeometryProxy.zh-Hans.md) to your own data type.
- action: This provides the data type you created in `of` and is called whenever the data type changes.

For example, you can use this modifier to know how much of a view is visible on screen. In the following example, the data type you convert to is a `Bool` and the action is called whenever the `Bool` changes.

```swift
ScrollView(.horizontal) {
    LazyHStack {
         ForEach(videos) { video in
             VideoView(video)
         }
     }
 }

struct VideoView: View {
    var video: VideoModel

    var body: some View {
        VideoPlayer(video)
            .onGeometryChange(for: Bool.self) { proxy in
                let frame = proxy.frame(in: .scrollView)
                let bounds = proxy.bounds(of: .scrollView) ?? .zero
                let intersection = frame.intersection(
                    CGRect(origin: .zero, size: bounds.size))
                let visibleHeight = intersection.size.height
                return (visibleHeight / frame.size.height) > 0.75
            } action: { isVisible in
                video.updateAutoplayingState(
                    isVisible: isVisible)
            }
    }
}
```

For easily responding to geometry changes of a scroll view, see the [onScrollGeometryChange(for:of:action:)](onScrollGeometryChange_for_of_action.zh-Hans.md) modifier.

