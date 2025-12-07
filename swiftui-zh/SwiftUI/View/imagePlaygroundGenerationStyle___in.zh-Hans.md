--- 来源：https://developer.apple.com/documentation/SwiftUI/View/imagePlaygroundGenerationStyle(_:in:)

抓取时间：2025-12-02T17:23:59Z

---

# imagePlaygroundGenerationStyle(_:in:)

**实例方法**

设置图像 Playground 的生成样式。

## 声明

```swift
nonisolated func imagePlaygroundGenerationStyle(_ style: ImagePlaygroundStyle, in allowedStyles: [ImagePlaygroundStyle] = ImagePlaygroundStyle.all) -> some View

```

## 参数

- **style**：Playground 使用的生成样式。

- **allowedStyles**：`style` 输入可以包含的生成样式列表。使用 `ImagePlaygroundStyle.all` 检查所有可能的样式列表，并传递其中的子集。

## 返回值

一个使用指定生成方式之一（`styles`）的图像演示工作表。


---
source: https://developer.apple.com/documentation/SwiftUI/View/imagePlaygroundGenerationStyle(_:in:)
crawled: 2025-12-02T17:23:59Z
---

# imagePlaygroundGenerationStyle(_:in:)

**Instance Method**

Sets the generation style for an image playground.

## Declaration

```swift
nonisolated func imagePlaygroundGenerationStyle(_ style: ImagePlaygroundStyle, in allowedStyles: [ImagePlaygroundStyle] = ImagePlaygroundStyle.all) -> some View

```

## Parameters

- **style**: The generation style that the playground uses.
- **allowedStyles**: The list of generation styles that the `style` input can have. Use `ImagePlaygroundStyle.all` to check the list of all possible styles, and pass a subset of those.

## Return Value

An image playground sheet that uses one of the specified generation `styles`.

