--- 来源：https://developer.apple.com/documentation/SwiftUI/View/preferredSurroundingsEffect(_:)

抓取时间：2025-12-02T16:22:08Z

---

# preferredSurroundingsEffect(_:)

**实例方法**

为透视视频应用效果。

## 声明

```swift
nonisolated func preferredSurroundingsEffect(_ effect: SurroundingsEffect?) -> some View

```

## 参数

- **effect**：要应用的效果。

## 返回值

显示指定效果的视图。

## 说明

使用此修饰符来指定显示修改后的视图时透视视频的外观偏好。例如，您可以通过将 [systemDark](../SurroundingsEffect/systemDark.zh-Hans.md) 首选项应用于场景内的某个视图，来增强使用默认 [mixed](../ImmersionStyle/mixed.zh-Hans.md) 沉浸式风格的场景的沉浸感：

```swift
ImmersiveSpace(id: "orbit") {
    Orbit()
        .preferredSurroundingsEffect(.dark)
}
```

当系统呈现上述代码中的 `Orbit` 视图时，它还会调暗透视视频。这有助于将注意力集中在场景的虚拟内容上，同时又能让用户保持对周围环境的感知。

使用值 `nil` 表示您没有首选项。通常，这样做是为了抵消视图层级结构中较低层级视图所表达的首选项。

## 配置透视

- **SurroundingsEffect**：系统可以应用于透视视频的效果。

- **BreakthroughEffect**


---
source: https://developer.apple.com/documentation/SwiftUI/View/preferredSurroundingsEffect(_:)
crawled: 2025-12-02T16:22:08Z
---

# preferredSurroundingsEffect(_:)

**Instance Method**

Applies an effect to passthrough video.

## Declaration

```swift
nonisolated func preferredSurroundingsEffect(_ effect: SurroundingsEffect?) -> some View

```

## Parameters

- **effect**: The effect that you want to apply.

## Return Value

A view that exhibits the specified preference.

## Discussion

Use this modifier to indicate a preference for the appearance of passthrough video when displaying the modified view. For example, you can enhance the immersiveness of a scene that uses the default [mixed](../ImmersionStyle/mixed.zh-Hans.md) immersion style by applying the [systemDark](../SurroundingsEffect/systemDark.zh-Hans.md) preference to a view inside the scene:

```swift
ImmersiveSpace(id: "orbit") {
    Orbit()
        .preferredSurroundingsEffect(.dark)
}
```

When the system presents the `Orbit` view in the above code, it also dims passthrough video. This helps to draw attention to the scene’s virtual content while still enabling people to remain aware of their surroundings.



Use a value of `nil` to indicate that you have no preference. You typically do this to counteract a preference expressed by a view lower in the view hierarchy.

## Configuring passthrough

- **SurroundingsEffect**: Effects that the system can apply to passthrough video.
- **BreakthroughEffect**

