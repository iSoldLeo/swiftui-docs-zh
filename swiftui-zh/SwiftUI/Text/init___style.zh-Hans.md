--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/init(_:style:)

抓取时间：2025-12-01T02:39:08Z

---

# init(_:style:)

**Initializer**

创建一个使用特定样式显示本地化日期和时间的实例。

## 声明

```swift
init(_ date: Date, style: Text.DateStyle)
```

## 参数

- **date**：要显示的目标日期。

- **style**：显示日期时使用的样式。

## 创建文本视图

- **init(_:tableName:bundle:comment:)**：创建一个显示由键标识的本地化内容的文本视图。

- **init(_:)**：创建一个文本视图，用于显示带样式的属性内容。

- **init(verbatim:)**：创建一个文本视图，用于显示不带本地化的字符串字面量。

- **init(_:format:)**：创建一个文本视图，用于显示受相应格式样式支持的非字符串类型的格式化表示。

- **init(_:formatter:)**：创建一个文本视图，用于显示 Foundation 对象的格式化表示。

- **init(timerInterval:pauseTime:countsDown:showsHours:)**：创建一个实例，用于显示指定时间间隔内的计时器。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/init(_:style:)
crawled: 2025-12-01T02:39:08Z
---

# init(_:style:)

**Initializer**

Creates an instance that displays localized dates and times using a specific style.

## Declaration

```swift
init(_ date: Date, style: Text.DateStyle)
```

## Parameters

- **date**: The target date to display.
- **style**: The style used when displaying a date.

## Creating a text view

- **init(_:tableName:bundle:comment:)**: Creates a text view that displays localized content identified by a key.
- **init(_:)**: Creates a text view that displays styled attributed content.
- **init(verbatim:)**: Creates a text view that displays a string literal without localization.
- **init(_:format:)**: Creates a text view that displays the formatted representation of a nonstring type supported by a corresponding format style.
- **init(_:formatter:)**: Creates a text view that displays the formatted representation of a Foundation object.
- **init(timerInterval:pauseTime:countsDown:showsHours:)**: Creates an instance that displays a timer counting within the provided interval.

