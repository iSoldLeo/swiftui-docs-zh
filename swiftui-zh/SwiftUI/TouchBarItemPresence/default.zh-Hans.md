---
来源： https://developer.apple.com/documentation/SwiftUI/TouchBarItemPresence/default(_:)
抓取时间： 2025-12-01T11:35:52Z
---

# TouchBarItemPresence.default(_:)

**Case**

默认情况下触摸栏视图是可见的，但可以在自定义时移除。

## 声明

```swift
case `default`(String)
```

## 参数

- **id**：此项目的全局唯一标识符。

## 获取存在选项

- **TouchBarItemPresence.optional(_:)**：默认情况下触摸栏视图不可见，但会出现在自定义调板中。
- **TouchBarItemPresence.required(_:)**：默认情况下触摸栏视图可见，且在自定义过程中无法移除。


---
source: https://developer.apple.com/documentation/SwiftUI/TouchBarItemPresence/default(_:)
crawled: 2025-12-01T11:35:52Z
---

# TouchBarItemPresence.default(_:)

**Case**

The Touch Bar view is visible by default, but can be removed during customization.

## Declaration

```swift
case `default`(String)
```

## Parameters

- **id**: A globally unique identifier for this item.

## Getting presence options

- **TouchBarItemPresence.optional(_:)**: The Touch Bar view isn’t visible by default, but appears in the customization palette.
- **TouchBarItemPresence.required(_:)**: The Touch Bar view is visible by default and cannot be removed during customization.

