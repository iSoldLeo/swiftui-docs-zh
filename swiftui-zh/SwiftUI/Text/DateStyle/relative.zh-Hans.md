--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/relative
抓取时间：2025-12-03T19:59:19Z

---

# relative

**类型属性**

一种将日期显示为相对于当前时间的样式。

## 声明

```swift
static let relative: Text.DateStyle
```

## 讨论

```swift
Text(event.startDate, style: .relative)
```

示例输出：2 小时 23 分钟 1 年 1 个月

## 获取文本日期样式

- **date**：一种显示日期的样式。

- **offset**：一种将日期显示为相对于当前时间的偏移量的样式。

- **time**：一种仅显示日期时间部分的样式。

- **timer**：一种以倒计时形式显示日期的样式，倒计时从现在开始。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/relative
crawled: 2025-12-03T19:59:19Z
---

# relative

**Type Property**

A style displaying a date as relative to now.

## Declaration

```swift
static let relative: Text.DateStyle
```

## Discussion

```swift
Text(event.startDate, style: .relative)
```

Example output: 2 hours, 23 minutes 1 year, 1 month

## Getting text date styles

- **date**: A style displaying a date.
- **offset**: A style displaying a date as offset from now.
- **time**: A style displaying only the time component for a date.
- **timer**: A style displaying a date as timer counting from now.

