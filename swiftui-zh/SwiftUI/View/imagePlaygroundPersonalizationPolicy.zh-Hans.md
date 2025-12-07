--- 来源：https://developer.apple.com/documentation/SwiftUI/View/imagePlaygroundPersonalizationPolicy(_:)

抓取时间：2025-11-30T21:09:03Z

---

# imagePlaygroundPersonalizationPolicy(_:)

**实例方法**

用于确定是否支持在 Playground 中使用人物的策略。

## 声明

```swift
nonisolated func imagePlaygroundPersonalizationPolicy(_ policy: ImagePlaygroundPersonalizationPolicy = .automatic) -> some View

```

## 参数

- **policy**：用于确定是否启用个性化的策略。

## 返回值

根据 `enabled` 标志，返回一个支持或不支持个性化的图像 Playground 工作表。

## 讨论

启用人物支持后，用户可以使用以下方式筛选图像生成：

- 系统照片库中的人物

- 由外貌和肤色表示的角色

个性化选项可通过多种用户界面访问，包括：

- 人物选择器

- 检测提示文本字段中的人物姓名

- 从系统照片库导入包含人脸的图像

默认情况下，当未设置修饰符或策略设置为 `automatic` 时，此功能处于启用状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/imagePlaygroundPersonalizationPolicy(_:)
crawled: 2025-11-30T21:09:03Z
---

# imagePlaygroundPersonalizationPolicy(_:)

**Instance Method**

Policy determining whether to support the usage of people in the playground or not.

## Declaration

```swift
nonisolated func imagePlaygroundPersonalizationPolicy(_ policy: ImagePlaygroundPersonalizationPolicy = .automatic) -> some View

```

## Parameters

- **policy**: Policy determining whether personalization is enabled or not.

## Return Value

An image playground sheet that does or does not support personalization, based on the `enabled` flag.

## Discussion

Enabling people support will allow the user to condition image generation using:

- A person from their system Photos library
- A character represented by an appearance and a skin tone

Personalization options are available through several user interfaces, including:

- A people picker
- Detection of people names in the prompt text field
- Importing images containing people faces from the system photo library

Enabled by default when the modifier is not set or when the policy is set to `automatic`.

