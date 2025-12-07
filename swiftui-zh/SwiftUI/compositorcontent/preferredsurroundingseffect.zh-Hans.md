--- 来源：https://developer.apple.com/documentation/swiftui/compositorcontent/preferredsurroundingseffect(_:)

抓取时间：2025-12-01T11:21:51Z

---

# preferredSurroundingsEffect(_:)

**实例方法**

为直通视频应用效果。

## 声明

```swift
nonisolated func preferredSurroundingsEffect(_ effect: SurroundingsEffect?) -> some CompositorContent

```

## 参数

- **effect**：要应用的效果。

## 返回值

一个应用了指定效果的 CompositorContent。

## 说明

使用此修饰符可以指定在显示修改后的合成器内容时，直通视频的外观偏好。例如，您可以将 [systemDark](../SurroundingsEffect/systemDark.zh-Hans.md) 首选项应用于场景内的合成器内容，从而增强使用默认 [mixed](../ImmersionStyle/mixed.zh-Hans.md) 沉浸式风格的场景的沉浸感。

这还会降低透传视频的亮度，有助于将注意力集中在场景的虚拟内容上，同时又能让用户保持对周围环境的感知。

使用 `nil` 值表示您没有首选项。通常，这样做是为了抵消视图层级结构中较低层级所表达的首选项。


---
source: https://developer.apple.com/documentation/swiftui/compositorcontent/preferredsurroundingseffect(_:)
crawled: 2025-12-01T11:21:51Z
---

# preferredSurroundingsEffect(_:)

**Instance Method**

Applies an effect to passthrough video.

## Declaration

```swift
nonisolated func preferredSurroundingsEffect(_ effect: SurroundingsEffect?) -> some CompositorContent

```

## Parameters

- **effect**: The effect that you want to apply.

## Return Value

A CompositorContent that exhibits the specified preference.

## Discussion

Use this modifier to indicate a preference for the appearance of passthrough video when displaying the modified compositor content. For example, you can enhance the immersiveness of a scene that uses the default [mixed](../ImmersionStyle/mixed.zh-Hans.md) immersion style by applying the [systemDark](../SurroundingsEffect/systemDark.zh-Hans.md) preference to a compositor content inside the scene.

This also dims passthrough video, which helps to draw attention to the scene’s virtual content while still enabling people to remain aware of their surroundings.



Use a value of `nil` to indicate that you have no preference. You typically do this to counteract a preference expressed by something lower in the view hierarchy.

