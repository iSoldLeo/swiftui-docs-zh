---
来源： https://developer.apple.com/documentation/SwiftUI/PaletteSelectionEffect/automatic
抓取时间： 2025-12-03T06:22:02Z
---

# 自动

**类型属性**

选中时应用系统默认效果。

## 声明

```swift
static let automatic: PaletteSelectionEffect
```

## 讨论

使用未着色的 SF 符号或模板图像时，当前的着色会应用到所选项目的图像上。如果所提供的 SF 符号具有自定义色调，则会在所选项目周围绘制描边。

## 获取调色板选择效果

- **custom**：选中时不应用任何系统效果。
- **symbolVariant(_:)**：选择时应用指定的符号变体。


---
source: https://developer.apple.com/documentation/SwiftUI/PaletteSelectionEffect/automatic
crawled: 2025-12-03T06:22:02Z
---

# automatic

**Type Property**

Applies the system’s default effect when selected.

## Declaration

```swift
static let automatic: PaletteSelectionEffect
```

## Discussion

When using un-tinted SF Symbols or template images, the current tint color is applied to the selected items’ image. If the provided SF Symbols have custom tints, a stroke is drawn around selected items.

## Getting palette selection effects

- **custom**: Does not apply any system effect when selected.
- **symbolVariant(_:)**: Applies the specified symbol variant when selected.

