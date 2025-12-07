--- 来源：https://developer.apple.com/documentation/SwiftUI/View/writingToolsAffordanceVisibility(_:)

抓取时间：2025-12-02T17:26:28Z

---

# writingToolsAffordanceVisibility(_:)

**实例方法**

指定系统是否应为受环境影响的文本输入视图显示“写作工具”辅助功能。

## 声明

```swift
@MainActor @preconcurrency func writingToolsAffordanceVisibility(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：是否允许为文本输入视图显示辅助功能。

## 返回值

具有指定“写作工具”辅助功能可见性的视图。

## 说明

在 macOS 或 Mac Catalyst 上运行时，使用此视图修饰符可禁用视图的“写作工具”辅助功能。


---
source: https://developer.apple.com/documentation/SwiftUI/View/writingToolsAffordanceVisibility(_:)
crawled: 2025-12-02T17:26:28Z
---

# writingToolsAffordanceVisibility(_:)

**Instance Method**

Specifies whether the system should show the Writing Tools affordance for text input views affected by the environment.

## Declaration

```swift
@MainActor @preconcurrency func writingToolsAffordanceVisibility(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: Whether the affordance may be shown for text input views.

## Return Value

A view with the specified Writing Tools affordance visibility.

## Discussion

Use this view modifier to disable the Writing Tools affordance for [TextField](../TextField.zh-Hans.md) views when running on macOS or Mac Catalyst.

