---
来源： https://developer.apple.com/documentation/swiftui/systemformatstyle/datereference
抓取时间： 2025-12-05T22:23:38Z
---

# SystemFormatStyle.DateReference

**Structure**

系统格式样式，用于以最自然的方式引用日期。

## 声明

```swift
struct DateReference
```

## 概览

参考格式旨在以最自然的方式引用某个日期。具体格式取决于与日期的距离。例如，如果事件发生在一分钟后，大多数人会用相对的方式来表示，如事件在 "一分钟后 "开始。但是，如果日期真的很遥远，那么用绝对的方式来表示就比较容易，例如，iPhone 的发布时间是 "2007 年 1 月"。

使用该样式时，应将其初始化为应引用的日期，并使用参考点（通常是当前时间）进行格式化。

## 初始化程序

- **init(to:allowedFields:maxFieldCount:thresholdField:)**：创建格式样式，以最自然的方式引用日期。

### 实例方法

- **calendar(_:)**

## 符合

- 可复制
- 可解码
- 离散格式样式
- 可编码
- 可等价
- 格式样式
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/systemformatstyle/datereference
crawled: 2025-12-05T22:23:38Z
---

# SystemFormatStyle.DateReference

**Structure**

A system format style to refer to a date in the most natural way.

## Declaration

```swift
struct DateReference
```

## Overview

The reference format is designed for referring to a certain date in the most natural way possible. The concrete format depends on the distance to the date. E.g. if an event is one minute away, most people would refer to it in a relative way, e.g. the event starts “in one minute”. However, if dates are really far away, it becomes easier to refer to them in an absolute way, e.g. the original iPhone was announced in “January 2007”.

Use the style by initializing it with the date it should refer to and format it with the point of reference, usually the current time.

## Initializers

- **init(to:allowedFields:maxFieldCount:thresholdField:)**: Create a format style to refer to a date in the most natural way.

## Instance Methods

- **calendar(_:)**

## Conforms To

- Copyable
- Decodable
- DiscreteFormatStyle
- Encodable
- Equatable
- FormatStyle
- Hashable
- Sendable
- SendableMetatype

