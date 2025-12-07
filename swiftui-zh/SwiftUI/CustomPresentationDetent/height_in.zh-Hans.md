--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomPresentationDetent/height(in:)

抓取时间：2025-12-01T10:51:31Z

---

# height(in:)

**类型方法**

根据上下文计算并返回高度。

## 声明

```swift
static func height(in context: Self.Context) -> CGFloat?
```

## 参数

- **context**：用于确定定位销高度的信息。

## 返回值

定位销的高度，或者，如果根据 `contenxt` 输入，定位销应处于非活动状态，则返回 `nil`。

## 获取高度

- **CustomPresentationDetent.Context**：可用于计算自定义定位销高度的信息。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomPresentationDetent/height(in:)
crawled: 2025-12-01T10:51:31Z
---

# height(in:)

**Type Method**

Calculates and returns a height based on the context.

## Declaration

```swift
static func height(in context: Self.Context) -> CGFloat?
```

## Parameters

- **context**: Information that can help to determine the height of the detent.

## Return Value

The height of the detent, or `nil` if the detent should be inactive based on the `contenxt` input.

## Getting the height

- **CustomPresentationDetent.Context**: Information that you can use to calculate the height of a custom detent.

