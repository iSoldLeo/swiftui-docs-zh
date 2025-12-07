--- 来源：https://developer.apple.com/documentation/SwiftUI/GlassBackgroundDisplayMode/implicit
抓取时间：2025-12-03T06:11:52Z

---

# GlassBackgroundDisplayMode.implicit

**Case**

仅当视图本身不包含在玻璃材质中时才显示玻璃材质。

## 声明

```swift
case implicit
```

## 讨论

当一个具有玻璃背景的视图包含另一个也具有玻璃背景的视图时，使用此值可以避免出现重复的背景。

对于沿 z 轴偏移任意值的视图，此显示模式不会抑制重复的玻璃背景。例如，以下视图 [HStack](../HStack.zh-Hans.md) 的两个子视图的行为有所不同：

```swift
HStack {
    MyView()
        .glassBackgroundEffect(displayMode: .implicit)
    MyView()
        .glassBackgroundEffect(displayMode: .implicit)
        .offset(z: 100)
}
.glassBackgroundEffect(displayMode: .always)
```

`MyView` 的第一个实例不显示背景，因为它的容器视图显示了背景。但是，第二个实例显示了背景，因为该视图沿 z 轴方向与其容器视图偏移了 100 个点。

## 获取模式

- **GlassBackgroundDisplayMode.always**：始终显示玻璃材质。

- **GlassBackgroundDisplayMode.never**：从不显示玻璃材质。


---
source: https://developer.apple.com/documentation/SwiftUI/GlassBackgroundDisplayMode/implicit
crawled: 2025-12-03T06:11:52Z
---

# GlassBackgroundDisplayMode.implicit

**Case**

Display the glass material only when the view isn’t already contained in glass.

## Declaration

```swift
case implicit
```

## Discussion

Use this value to avoid duplicate backgrounds when a view that has a glass background contains another view that also has a glass background.

This display mode doesn’t suppress duplicate glass backgrounds for views that are offset by any amount in the z-axis. For example, the two subviews of the following [HStack](../HStack.zh-Hans.md) behave differently:

```swift
HStack {
    MyView()
        .glassBackgroundEffect(displayMode: .implicit)
    MyView()
        .glassBackgroundEffect(displayMode: .implicit)
        .offset(z: 100)
}
.glassBackgroundEffect(displayMode: .always)
```

The first instance of `MyView` doesn’t display a background because its container displays one. However the second instance does display a background because that view is offset from its container by 100 points along the z-axis.

## Getting the mode

- **GlassBackgroundDisplayMode.always**: Always display the glass material.
- **GlassBackgroundDisplayMode.never**: Never display the glass material.

