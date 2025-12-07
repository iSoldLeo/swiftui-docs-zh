--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/date
抓取时间：2025-12-03T19:59:18Z

---

# date

**类型属性**

一种显示日期的样式。

## 声明

```swift
static let date: Text.DateStyle
```

## 讨论

```swift
Text(event.startDate, style: .date)
```

示例输出：2019年6月3日

## 获取文本日期样式

- **offset**：一种显示日期相对于当前时间偏移量的样式。

- **relative**：一种显示日期相对于当前时间的样式。

- **time**：一种仅显示日期时间部分的样式。

- **timer**：一种以倒计时形式显示日期的样式，倒计时从现在开始。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/date
crawled: 2025-12-03T19:59:18Z
---

# date

**Type Property**

A style displaying a date.

## Declaration

```swift
static let date: Text.DateStyle
```

## Discussion

```swift
Text(event.startDate, style: .date)
```

Example output: June 3, 2019

## Getting text date styles

- **offset**: A style displaying a date as offset from now.
- **relative**: A style displaying a date as relative to now.
- **time**: A style displaying only the time component for a date.
- **timer**: A style displaying a date as timer counting from now.

