--- 来源：https://developer.apple.com/documentation/SwiftUI/View/backgroundExtensionEffect(isEnabled:)

抓取时间：2025-11-30T21:07:39Z

---

# backgroundExtensionEffect(isEnabled:)

**实例方法**

为视图添加背景扩展效果。视图将被复制成镜像副本，并放置在视图周围任何可用的安全区域边缘。此外，还会对副本应用模糊效果。

## 声明

```swift
@MainActor @preconcurrency func backgroundExtensionEffect(isEnabled: Bool) -> some View

```

## 参数

- **isEnabled**：是否启用扩展效果。

## 说明

当您希望在安全区域之外创建副本时，请使用此修饰符，以便视图及其副本可以共同作为上方其他元素的背景。最常见的用法是将其应用于导航拆分视图的详情列中的视图，使其可以延伸到侧边栏或检查器区域下方，从而提供无缝沉浸式视觉效果。

```swift
@State private var extendBackground: Bool = true

NavigationSplitView {
    // sidebar content
} detail: {
    ZStack {
        BannerView()
            .backgroundExtensionEffect(isEnabled: extendBackground)
    }
}
.inspector(isPresented: $showInspector) {
    // inspector content
}
```

请谨慎使用此修饰符。通常情况下，应仅将其用于单个背景内容实例，并兼顾视觉清晰度和性能。


---
source: https://developer.apple.com/documentation/SwiftUI/View/backgroundExtensionEffect(isEnabled:)
crawled: 2025-11-30T21:07:39Z
---

# backgroundExtensionEffect(isEnabled:)

**Instance Method**

Adds the background extension effect to the view. The view will be duplicated into mirrored copies which will be placed around the view on any edge with available safe area. Additionally, a blur effect will be applied on top to blur out the copies.

## Declaration

```swift
@MainActor @preconcurrency func backgroundExtensionEffect(isEnabled: Bool) -> some View

```

## Parameters

- **isEnabled**: Should the extension effect be active or not.

## Discussion

Use this modifier when you want to create copies outside of the safe area so the view and its copies together can function as backgrounds for other elements on top. The most common use case is to apply this to a view in the detail column of a navigation split view so it can extend under the sidebar or inspector region to provide seamless immersive visuals.

```swift
@State private var extendBackground: Bool = true

NavigationSplitView {
    // sidebar content
} detail: {
    ZStack {
        BannerView()
            .backgroundExtensionEffect(isEnabled: extendBackground)
    }
}
.inspector(isPresented: $showInspector) {
    // inspector content
}
```

Apply this modifier with discretion. This should often be used with only a single instance of background content with consideration of visual clarity and performance.



