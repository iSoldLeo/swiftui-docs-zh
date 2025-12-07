---
来源： https://developer.apple.com/documentation/SwiftUI/TouchBarItemPresence/required(_:)
抓取时间： 2025-12-03T06:46:45Z
---

# TouchBarItemPresence.required(_:)

**Case**

触摸栏视图默认为可见，在自定义过程中无法移除。

## 声明

```swift
case required(String)
```

## 参数

- **id**：此项目的全局唯一标识符。

## 获取存在选项

- **TouchBarItemPresence.default(_:)**：默认情况下触摸栏视图是可见的，但可以在自定义时移除。
- **TouchBarItemPresence.optional(_:)**：默认情况下触摸栏视图不可见，但会出现在自定义调板中。


---
source: https://developer.apple.com/documentation/SwiftUI/TouchBarItemPresence/required(_:)
crawled: 2025-12-03T06:46:45Z
---

# TouchBarItemPresence.required(_:)

**Case**

The Touch Bar view is visible by default and cannot be removed during customization.

## Declaration

```swift
case required(String)
```

## Parameters

- **id**: A globally unique identifier for this item.

## Getting presence options

- **TouchBarItemPresence.default(_:)**: The Touch Bar view is visible by default, but can be removed during customization.
- **TouchBarItemPresence.optional(_:)**: The Touch Bar view isn’t visible by default, but appears in the customization palette.

