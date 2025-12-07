--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/timer
抓取时间：2025-12-03T19:59:21Z

---

# timer

**类型属性**

一种样式，用于显示从当前时间开始的倒计时日期。

## 声明

```swift
static let timer: Text.DateStyle
```

## 讨论

```swift
Text(event.startDate, style: .timer)
```

示例输出：2:32 36:59:01

## 获取文本日期样式

- **date**：一种显示日期的样式。

- **offset**：一种显示日期相对于当前时间的偏移量的样式。

- **relative**：一种显示日期相对于当前时间的相对值的样式。

- **time**：一种仅显示日期时间部分的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/timer
crawled: 2025-12-03T19:59:21Z
---

# timer

**Type Property**

A style displaying a date as timer counting from now.

## Declaration

```swift
static let timer: Text.DateStyle
```

## Discussion

```swift
Text(event.startDate, style: .timer)
```

Example output: 2:32 36:59:01

## Getting text date styles

- **date**: A style displaying a date.
- **offset**: A style displaying a date as offset from now.
- **relative**: A style displaying a date as relative to now.
- **time**: A style displaying only the time component for a date.

