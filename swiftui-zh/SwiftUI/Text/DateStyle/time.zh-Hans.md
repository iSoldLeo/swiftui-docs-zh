--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/time
抓取时间：2025-12-03T19:59:20Z

---

# time

**类型属性**

仅显示日期时间部分的样式。

## 声明

```swift
static let time: Text.DateStyle
```

## 讨论

```swift
Text(event.startDate, style: .time)
```

示例输出：11:23PM

## 获取文本日期样式

- **date**：显示日期的样式。

- **offset**：显示日期相对于当前时间的偏移量的样式。

- **relative**：显示日期相对于当前时间的相对值的样式。

- **timer**：一种以倒计时形式显示日期的样式，倒计时从现在开始。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/DateStyle/time
crawled: 2025-12-03T19:59:20Z
---

# time

**Type Property**

A style displaying only the time component for a date.

## Declaration

```swift
static let time: Text.DateStyle
```

## Discussion

```swift
Text(event.startDate, style: .time)
```

Example output: 11:23PM

## Getting text date styles

- **date**: A style displaying a date.
- **offset**: A style displaying a date as offset from now.
- **relative**: A style displaying a date as relative to now.
- **timer**: A style displaying a date as timer counting from now.

