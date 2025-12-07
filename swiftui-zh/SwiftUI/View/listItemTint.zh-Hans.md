--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listItemTint(_:)

抓取时间：2025-11-30T21:24:37Z

---

# listItemTint(_:)

**实例方法**

为列表内容设置固定的着色颜色。

## 声明

```swift
nonisolated func listItemTint(_ tint: Color?) -> some View

```

## 参数

- **tint**：用于为内容着色的颜色。使用 `nil` 可避免覆盖继承的着色。

## 说明

包含列表的样式会根据需要应用此着色。例如，watchOS 会将此着色颜色用于其背景面板外观。 iOS 和 macOS 的侧边栏会将着色效果应用于其 [Label](../Label.zh-Hans.md) 图标，这些图标默认使用强调色。

## 配置行

- **ListItemTint**：可应用于列表内容的着色效果配置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listItemTint(_:)
crawled: 2025-11-30T21:24:37Z
---

# listItemTint(_:)

**Instance Method**

Sets a fixed tint color for content in a list.

## Declaration

```swift
nonisolated func listItemTint(_ tint: Color?) -> some View

```

## Parameters

- **tint**: The color to use to tint the content. Use `nil` to avoid overriding the inherited tint.

## Discussion

The containing list’s style applies the tint as appropriate. For example, watchOS uses the tint color for its background platter appearance. Sidebars on iOS and macOS apply the tint color to their [Label](../Label.zh-Hans.md) icons, which otherwise use the accent color by default.



## Configuring rows

- **ListItemTint**: A tint effect configuration that you can apply to content in a list.

