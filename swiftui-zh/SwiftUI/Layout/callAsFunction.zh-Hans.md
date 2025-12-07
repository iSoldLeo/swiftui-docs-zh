---
来源： https://developer.apple.com/documentation/SwiftUI/Layout/callAsFunction(_:)
抓取时间： 2025-12-02T17:53:12Z
---

# callAsFunction(_:)

**实例方法**

使用自定义布局容器的布局算法将指定视图组合成一个复合视图。

## 声明

```swift
func callAsFunction<V>(@ViewBuilder _ content: () -> V) -> some View where V : View

```

## 参数

- **content**：包含要布局的视图的[ViewBuilder](../ViewBuilder.zh-Hans.md)。

## 返回值

合并所有输入视图的复合视图。

## 讨论

不要直接调用此方法。SwiftUI 会在实例化符合[Layout](../Layout.zh-Hans.md) 协议的自定义布局时调用该方法：

```swift
BasicVStack { // Implicitly calls callAsFunction.
    Text("A View")
    Text("Another View")
}
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/callAsFunction(_:)
crawled: 2025-12-02T17:53:12Z
---

# callAsFunction(_:)

**Instance Method**

Combines the specified views into a single composite view using the layout algorithms of the custom layout container.

## Declaration

```swift
func callAsFunction<V>(@ViewBuilder _ content: () -> V) -> some View where V : View

```

## Parameters

- **content**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that contains the views to lay out.

## Return Value

A composite view that combines all the input views.

## Discussion

Don’t call this method directly. SwiftUI calls it when you instantiate a custom layout that conforms to the [Layout](../Layout.zh-Hans.md) protocol:

```swift
BasicVStack { // Implicitly calls callAsFunction.
    Text("A View")
    Text("Another View")
}
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

