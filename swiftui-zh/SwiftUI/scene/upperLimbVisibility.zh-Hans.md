--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/upperLimbVisibility(_:)

抓取时间：2025-12-02T17:21:57Z

---

# upperLimbVisibility(_:)

**实例方法**

设置用户上肢在呈现 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 场景时的首选可见性。

## 声明

```swift
nonisolated func upperLimbVisibility(_ preferredVisibility: Visibility) -> some Scene

```

## 参数

- **preferredVisibility**：指示上肢是否可见的值。使用 `.automatic` 表示系统定义的标准行为，使用 `.visible` 表示保持上肢可见，使用 `.hidden` 表示隐藏上肢。

## 讨论

系统可以在完全沉浸式体验中显示用户的上肢，但您也可以将其隐藏，例如，以便显示虚拟手部。

请注意，此参数仅设置偏好，最终是否遵循此设置将由系统决定。如果沉浸式空间当前不可见，系统可能无法遵循此偏好。

## 沉浸式体验中隐藏上肢

- **upperLimbVisibility(_:)**：设置呈现 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 场景时用户上肢的首选可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/upperLimbVisibility(_:)
crawled: 2025-12-02T17:21:57Z
---

# upperLimbVisibility(_:)

**Instance Method**

Sets the preferred visibility of the user’s upper limbs, while an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) scene is presented.

## Declaration

```swift
nonisolated func upperLimbVisibility(_ preferredVisibility: Visibility) -> some Scene

```

## Parameters

- **preferredVisibility**: A value indicating if the upper limbs should be visible. Use `.automatic` for a system-defined standard behavior, `.visible` to keep the upper limbs visible, and `.hidden` to hide the upper limbs.

## Discussion

The system can show the user’s upper limbs during fully immersive experiences, but you can also hide them, for example, in order to display virtual hands instead.

Note that this modifier only sets a preference and ultimately the system will decide if it will honor it or not. The system may be unable to honor the preference if the immersive space is currently not visible.

## Hiding upper limbs during immersion

- **upperLimbVisibility(_:)**: Sets the preferred visibility of the user’s upper limbs, while an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) scene is presented.

