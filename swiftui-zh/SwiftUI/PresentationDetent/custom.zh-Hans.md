---
来源： https://developer.apple.com/documentation/SwiftUI/PresentationDetent/custom(_:)
抓取时间： 2025-12-03T06:02:28Z
---

# custom(_:)

**类型方法**

自定义制动装置，高度经过计算。

## 声明

```swift
static func custom<D>(_ type: D.Type) -> PresentationDetent where D : CustomPresentationDetent
```

## 创建自定义制动器

- **fraction(_:)**：具有指定分数高度的自定义制动块。
- **height(_:)**：具有指定高度的定制制动块。
- **PresentationDetent.Context**：用于计算演示高度的信息。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationDetent/custom(_:)
crawled: 2025-12-03T06:02:28Z
---

# custom(_:)

**Type Method**

A custom detent with a calculated height.

## Declaration

```swift
static func custom<D>(_ type: D.Type) -> PresentationDetent where D : CustomPresentationDetent
```

## Creating custom detents

- **fraction(_:)**: A custom detent with the specified fractional height.
- **height(_:)**: A custom detent with the specified height.
- **PresentationDetent.Context**: Information that you use to calculate the presentation’s height.

