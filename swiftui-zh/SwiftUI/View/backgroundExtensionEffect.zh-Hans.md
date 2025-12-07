---

来源：https://developer.apple.com/documentation/SwiftUI/View/backgroundExtensionEffect()

抓取时间：2025-11-30T21:07:38Z

---

# backgroundExtensionEffect()

**实例方法**

为视图添加背景扩展效果。视图将被复制成镜像副本，并放置在视图周围任何可用的安全区域边缘。此外，还会对副本应用模糊效果。

## 声明

```swift
@MainActor @preconcurrency func backgroundExtensionEffect() -> some View

```

## 讨论

当您希望将视图扩展到其边界之外时，可以使用此修饰符，以便副本可以作为上方其他元素的背景。最常见的用例是将其应用于导航拆分视图的详情列中的视图，使其可以扩展到侧边栏或检查器区域下方，从而提供无缝沉浸式视觉效果。

```swift
NavigationSplitView {
    // sidebar content
} detail: {
    ZStack {
        BannerView()
            .backgroundExtensionEffect()
    }
}
.inspector(isPresented: $showInspector) {
    // inspector content
}
```

请谨慎使用此修饰符。通常情况下，应仅用于单个背景内容，并需兼顾视觉清晰度和性能。


---
source: https://developer.apple.com/documentation/SwiftUI/View/backgroundExtensionEffect()
crawled: 2025-11-30T21:07:38Z
---

# backgroundExtensionEffect()

**Instance Method**

Adds the background extension effect to the view. The view will be duplicated into mirrored copies which will be placed around the view on any edge with available safe area. Additionally, a blur effect will be applied on top to blur out the copies.

## Declaration

```swift
@MainActor @preconcurrency func backgroundExtensionEffect() -> some View

```

## Discussion

Use this modifier when you want to extend the view beyond its bounds so the copies can function as backgrounds for other elements on top. The most common use case is to apply this to a view in the detail column of a navigation split view so it can extend under the sidebar or inspector region to provide seamless immersive visuals.

```swift
NavigationSplitView {
    // sidebar content
} detail: {
    ZStack {
        BannerView()
            .backgroundExtensionEffect()
    }
}
.inspector(isPresented: $showInspector) {
    // inspector content
}
```

Apply this modifier with discretion. This should often be used with only a single instance of background content with consideration of visual clarity and performance.



