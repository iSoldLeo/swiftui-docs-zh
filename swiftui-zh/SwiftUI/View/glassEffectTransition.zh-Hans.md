---

来源：https://developer.apple.com/documentation/SwiftUI/View/glassEffectTransition(_:)

抓取时间：2025-11-30T21:08:55Z

---

# glassEffectTransition(_:)

**实例方法**

将玻璃效果过渡与此视图中定义的任何玻璃效果关联起来。

## 声明

```swift
@MainActor @preconcurrency func glassEffectTransition(_ transition: GlassEffectTransition) -> some View

```

## 说明

您可以将此修饰符与 [glassEffect(_:in:)](glassEffect___in.zh-Hans.md) 视图修饰符和 [GlassEffectContainer](../GlassEffectContainer.zh-Hans.md) 视图修饰符一起使用。当它们一起使用时，当您在视图层次结构中添加或移除具有这些效果的视图时，SwiftUI 将使用提供的过渡效果来应用玻璃效果的更改。

在下面的示例中，当 isExpanded 变量发生变化时，记事本图像将过渡到铅笔图像，然后再过渡回铅笔图像。

```swift
var isExpanded: Bool
@Namespace private var namespace

var body: some View {
    GlassEffectContainer(spacing: 10.0) {
        HStack(spacing: 10.0) {
            Image(systemName: "pencil")
                .frame(width: 20.0, height: 20.0)
                .glassEffect()
                .glassEffectID("pencil", in: namespace)

                if isExpanded {
                    Image(systemName: "note")
                        .frame(width: 20.0, height: 20.0)
                        .glassEffect()
                        .glassEffectID("note", in: namespace)
                        .glassEffectTransition(.matchedGeometry)
                }
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/glassEffectTransition(_:)
crawled: 2025-11-30T21:08:55Z
---

# glassEffectTransition(_:)

**Instance Method**

Associates a glass effect transition with any glass effects defined within this view.

## Declaration

```swift
@MainActor @preconcurrency func glassEffectTransition(_ transition: GlassEffectTransition) -> some View

```

## Discussion

You use this modifier with the [glassEffect(_:in:)](glassEffect___in.zh-Hans.md) view modifier and [GlassEffectContainer](../GlassEffectContainer.zh-Hans.md) view. When used together, SwiftUI will use the provided transition to apply changes to the glass effect when you add or remove views with these effects from the view hierarchy.

In the example below, the notepad image will transition into and out of the pencil image when the isExpanded variable changes.

```swift
var isExpanded: Bool
@Namespace private var namespace

var body: some View {
    GlassEffectContainer(spacing: 10.0) {
        HStack(spacing: 10.0) {
            Image(systemName: "pencil")
                .frame(width: 20.0, height: 20.0)
                .glassEffect()
                .glassEffectID("pencil", in: namespace)

                if isExpanded {
                    Image(systemName: "note")
                        .frame(width: 20.0, height: 20.0)
                        .glassEffect()
                        .glassEffectID("note", in: namespace)
                        .glassEffectTransition(.matchedGeometry)
                }
            }
        }
    }
}
```

