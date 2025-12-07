---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isPresented
抓取时间： 2025-12-02T17:31:01Z
---

# isPresented

**实例属性**

布尔值，表示与此环境相关的视图当前是否显示。

## 声明

```swift
var isPresented: Bool { get }
```

## 讨论

通过使用[Environment](../Environment.zh-Hans.md) 属性包装器创建属性，您可以像读取其他[EnvironmentValues](../EnvironmentValues.zh-Hans.md) 属性一样读取该值：

```swift
@Environment(\.isPresented) private var isPresented
```

如果需要知道 SwiftUI 何时显示视图，可以读取视图内部的值。例如，您可以使用 [onChange(of:initial:_:)](../View/onChange_of_initial.zh-Hans.md) 修饰符在 SwiftUI 显示视图时执行操作：

```swift
.onChange(of: isPresented) { _, isPresented in
    if isPresented {
        // Do something when first presented.
    }
}
```

这与[onAppear(perform:)](../View/onAppear_perform.zh-Hans.md) 的行为不同，SwiftUI 可以对给定的展示调用多次，例如当您导航回到已在导航层级中的视图时。

要取消当前显示的视图，请使用 [dismiss](dismiss.zh-Hans.md)。

## 解散演示文稿

- **dismiss**：解除当前演示的操作。
- **DismissAction**：解散演示文稿的操作。
- **interactiveDismissDisabled(_:)**：有条件地防止弹出窗口、工作表和检查器等演示文稿的交互式解散。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isPresented
crawled: 2025-12-02T17:31:01Z
---

# isPresented

**Instance Property**

A Boolean value that indicates whether the view associated with this environment is currently presented.

## Declaration

```swift
var isPresented: Bool { get }
```

## Discussion

You can read this value like any of the other [EnvironmentValues](../EnvironmentValues.zh-Hans.md) by creating a property with the [Environment](../Environment.zh-Hans.md) property wrapper:

```swift
@Environment(\.isPresented) private var isPresented
```

Read the value inside a view if you need to know when SwiftUI presents that view. For example, you can take an action when SwiftUI presents a view by using the [onChange(of:initial:_:)](../View/onChange_of_initial.zh-Hans.md) modifier:

```swift
.onChange(of: isPresented) { _, isPresented in
    if isPresented {
        // Do something when first presented.
    }
}
```

This behaves differently than [onAppear(perform:)](../View/onAppear_perform.zh-Hans.md), which SwiftUI can call more than once for a given presentation, like when you navigate back to a view that’s already in the navigation hierarchy.

To dismiss the currently presented view, use [dismiss](dismiss.zh-Hans.md).

## Dismissing a presentation

- **dismiss**: An action that dismisses the current presentation.
- **DismissAction**: An action that dismisses a presentation.
- **interactiveDismissDisabled(_:)**: Conditionally prevents interactive dismissal of presentations like popovers, sheets, and inspectors.

