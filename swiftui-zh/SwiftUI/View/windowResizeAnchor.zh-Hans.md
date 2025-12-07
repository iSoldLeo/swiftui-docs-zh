--- 来源：https://developer.apple.com/documentation/SwiftUI/View/windowResizeAnchor(_:)

抓取时间：2025-12-02T17:26:25Z

---

# windowResizeAnchor(_:)

**实例方法**

设置当视图大小发生变化，导致窗口必须调整大小时使用的窗口锚点。

## 声明

```swift
nonisolated func windowResizeAnchor(_ anchor: UnitPoint?) -> some View

```

## 参数

- **anchor**：在窗口内容大小变化引起的程序化大小变化下固定的窗口锚点。当 `nil` 时，默认值为系统定义的值。

## 返回值

一个在 `anchor` 时场景大小发生变化的视图。

## 讨论

在 SwiftUI 生命周期应用中，此修饰符可用于控制窗口在动画时的锚点：通过改变视图的大小来驱动窗口动画，从而改变窗口的大小。请注意，如果窗口大小正在减小且需要动画效果，通常需要（如果需要，可以暂时）将 [windowResizability(_:)](../scene/windowResizability.zh-Hans.md) 设置为 [contentSize](../WindowResizability/contentSize.zh-Hans.md)。

```swift
struct Scratchpad: App {
    var body: some Scene {
        WindowGroup {
            HeightResizingExample()
        }
        .windowResizability(.contentSize)
    }
}

struct HeightResizingExample: View {
    @State private var height: CGFloat = 300

    var body: some View {
        ZStack(alignment: .topLeading) {
            Color.red
                .overlay {
                    Text("Tap to toggle")
                        .foregroundStyle(.white)
                }
        }
        .onTapGesture {
            withAnimation(.easeInOut) {
                height = height == 300 ? 700 : 300
            }
        }
        .frame(width: 250, height: height)
        .windowResizeAnchor(.top)
    }
}
```

默认锚点因场景类型而异，当 `anchor` 为 nil 时使用。通常，它会解析到 `.topLeading` 角点。


---
source: https://developer.apple.com/documentation/SwiftUI/View/windowResizeAnchor(_:)
crawled: 2025-12-02T17:26:25Z
---

# windowResizeAnchor(_:)

**Instance Method**

Sets the window anchor point used when the size of the view changes such that the window must resize.

## Declaration

```swift
nonisolated func windowResizeAnchor(_ anchor: UnitPoint?) -> some View

```

## Parameters

- **anchor**: The window point fixed under programmatic size changes caused by the content size of the window changing. Defaults to a system defined value when `nil`.

## Return Value

A view whose scene resizes on `anchor`.

## Discussion

In SwiftUI life cycle apps, this modifier can be used to control how a window anchors when animating: drive window animations by changing the size of a view in a way that causes the window size to change. Note that if the window size is decreasing and an animation is desired, it is often necessary to (temporarily, if desired) set the [windowResizability(_:)](../scene/windowResizability.zh-Hans.md) to [contentSize](../WindowResizability/contentSize.zh-Hans.md).

```swift
struct Scratchpad: App {
    var body: some Scene {
        WindowGroup {
            HeightResizingExample()
        }
        .windowResizability(.contentSize)
    }
}

struct HeightResizingExample: View {
    @State private var height: CGFloat = 300

    var body: some View {
        ZStack(alignment: .topLeading) {
            Color.red
                .overlay {
                    Text("Tap to toggle")
                        .foregroundStyle(.white)
                }
        }
        .onTapGesture {
            withAnimation(.easeInOut) {
                height = height == 300 ? 700 : 300
            }
        }
        .frame(width: 250, height: height)
        .windowResizeAnchor(.top)
    }
}
```

The default anchor varies by scene type and is used when `anchor` is nil. Generally, it resolves to the `.topLeading` corner.





