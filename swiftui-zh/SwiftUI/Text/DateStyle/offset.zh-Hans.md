--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/offset
抓取时间：2025-12-03T19:59:19Z

---

# offset

**类型属性**

一种样式，用于显示相对于当前时间的偏移量。

## 声明

```swift
static let offset: Text.DateStyle
```

## 讨论

```swift
Text(event.startDate, style: .offset)
```

示例输出：+2 小时 -3 个月

## 获取文本日期样式

- **date**：一种显示日期的样式。

- **relative**：一种样式，用于显示相对于当前时间的日期。

- **time**：一种样式，仅显示日期的时间部分。

- **timer**：一种以倒计时形式显示日期的样式，倒计时从现在开始。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/offset
crawled: 2025-12-03T19:59:19Z
---

# offset

**Type Property**

A style displaying a date as offset from now.

## Declaration

```swift
static let offset: Text.DateStyle
```

## Discussion

```swift
Text(event.startDate, style: .offset)
```

Example output: +2 hours -3 months

## Getting text date styles

- **date**: A style displaying a date.
- **relative**: A style displaying a date as relative to now.
- **time**: A style displaying only the time component for a date.
- **timer**: A style displaying a date as timer counting from now.

