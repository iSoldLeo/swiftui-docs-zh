--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hidden()

抓取时间：2025-11-30T21:17:40Z

---

# hidden()

**实例方法**

无条件隐藏此视图。

## 声明

```swift
nonisolated func hidden() -> some View

```

## 返回值

一个隐藏的视图。

## 说明

隐藏的视图是不可见的，无法接收或响应交互。但是，它们仍然保留在视图层级结构中，并影响布局。如果您出于布局目的需要包含某个视图，但不希望它显示，请使用此修饰符。

```swift
HStack {
    Image(systemName: "a.circle.fill")
    Image(systemName: "b.circle.fill")
    Image(systemName: "c.circle.fill")
        .hidden()
    Image(systemName: "d.circle.fill")
}
```

第三个圆圈会占用空间，因为它仍然存在，但 SwiftUI 不会将其绘制到屏幕上。

如果要根据条件在视图层级结构中包含某个视图，请改用 `if` 语句：

```swift
VStack {
    HStack {
        Image(systemName: "a.circle.fill")
        Image(systemName: "b.circle.fill")
        if !isHidden {
            Image(systemName: "c.circle.fill")
        }
        Image(systemName: "d.circle.fill")
    }
    Toggle("Hide", isOn: $isHidden)
}
```

根据上例中由 [Toggle](../Toggle.zh-Hans.md) 实例控制的 `isHidden` 状态变量的当前值，SwiftUI 会绘制圆形或将其从布局中完全省略。

## 隐藏视图

- **opacity(_:)**：设置此视图的透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/hidden()
crawled: 2025-11-30T21:17:40Z
---

# hidden()

**Instance Method**

Hides this view unconditionally.

## Declaration

```swift
nonisolated func hidden() -> some View

```

## Return Value

A hidden view.

## Discussion

Hidden views are invisible and can’t receive or respond to interactions. However, they do remain in the view hierarchy and affect layout. Use this modifier if you want to include a view for layout purposes, but don’t want it to display.

```swift
HStack {
    Image(systemName: "a.circle.fill")
    Image(systemName: "b.circle.fill")
    Image(systemName: "c.circle.fill")
        .hidden()
    Image(systemName: "d.circle.fill")
}
```

The third circle takes up space, because it’s still present, but SwiftUI doesn’t draw it onscreen.



If you want to conditionally include a view in the view hierarchy, use an `if` statement instead:

```swift
VStack {
    HStack {
        Image(systemName: "a.circle.fill")
        Image(systemName: "b.circle.fill")
        if !isHidden {
            Image(systemName: "c.circle.fill")
        }
        Image(systemName: "d.circle.fill")
    }
    Toggle("Hide", isOn: $isHidden)
}
```

Depending on the current value of the `isHidden` state variable in the example above, controlled by the [Toggle](../Toggle.zh-Hans.md) instance, SwiftUI draws the circle or completely omits it from the layout.



## Hiding views

- **opacity(_:)**: Sets the transparency of this view.

