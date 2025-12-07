--- 来源：https://developer.apple.com/documentation/SwiftUI/View/animation(_:body:)

抓取时间：2025-11-30T21:18:57Z

---

# animation(_:body:)

**实例方法**

将给定的动画应用于 `body` 闭包内的所有可动画值。

## 声明

```swift
nonisolated func animation<V>(_ animation: Animation?, @ViewBuilder body: (PlaceholderContentView<Self>) -> V) -> some View where V : View

```

## 说明

应用于 `body` 内容的任何修饰符都将应用于此视图，而 `animation` 仅用于 `body` 中定义的修饰符。

以下代码使用 easeInOut 动画实现透明度变化，而 MyView 的内容则使用隐式事务的动画：

```swift
MyView(isActive: isActive)
    .animation(.easeInOut) { content in
        content.opacity(isActive ? 1.0 : 0.0)
    }
```

## 为视图添加基于状态的动画

- **animation(_:)**：当此视图发生变化时，应用指定的动画。

- **animation(_:value:)**：当指定的值发生变化时，应用指定的动画。


---
source: https://developer.apple.com/documentation/SwiftUI/View/animation(_:body:)
crawled: 2025-11-30T21:18:57Z
---

# animation(_:body:)

**Instance Method**

Applies the given animation to all animatable values within the `body` closure.

## Declaration

```swift
nonisolated func animation<V>(_ animation: Animation?, @ViewBuilder body: (PlaceholderContentView<Self>) -> V) -> some View where V : View

```

## Discussion

Any modifiers applied to the content of `body` will be applied to this view, and the `animation` will only be used on the modifiers defined in the `body`.

The following code animates the opacity changing with an easeInOut animation, while the contents of MyView are animated with the implicit transaction’s animation:

```swift
MyView(isActive: isActive)
    .animation(.easeInOut) { content in
        content.opacity(isActive ? 1.0 : 0.0)
    }
```

## Adding state-based animation to a view

- **animation(_:)**: Applies the given animation to this view when this view changes.
- **animation(_:value:)**: Applies the given animation to this view when the specified value changes.

