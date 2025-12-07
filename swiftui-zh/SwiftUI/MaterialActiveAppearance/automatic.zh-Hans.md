---
来源： https://developer.apple.com/documentation/SwiftUI/MaterialActiveAppearance/automatic
抓取时间： 2025-12-03T06:25:44Z
---

# 自动

**类型属性**

材料将根据上下文和平台惯例自动显示为活动或非活动。

## 声明

```swift
static let automatic: MaterialActiveAppearance
```

## 讨论

macOS 上的自动行为示例

- 用作`window`容器背景的材质在包含窗口处于非活动状态时将显示为非活动状态。
- 当包含窗口处于非活动状态时，`Material.bar` 材料将显示为非活动状态。
- 所有其他材料将显示为活动状态。

在所有其他平台上，材料始终显示为活动状态。


---
source: https://developer.apple.com/documentation/SwiftUI/MaterialActiveAppearance/automatic
crawled: 2025-12-03T06:25:44Z
---

# automatic

**Type Property**

Materials will automatically appear active or inactive based on context and platform convention.

## Declaration

```swift
static let automatic: MaterialActiveAppearance
```

## Discussion

Examples of automatic behavior on macOS:

- Materials used as a `window` container background will appear inactive when the containing window is inactive.
- `Material.bar` materials will appear inactive when the containing window is inactive.
- All other materials will appear as active.

Materials always appear as active on all other platforms.

