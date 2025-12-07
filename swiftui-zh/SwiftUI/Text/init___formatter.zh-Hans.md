--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/init(_:formatter:)

抓取时间：2025-12-02T21:48:18Z

---

# init(_:formatter:)

**Initializer**

创建一个文本视图，用于显示 Foundation 对象的格式化表示形式。

## 声明

```swift
init<Subject>(_ subject: Subject, formatter: Formatter) where Subject : NSObject
```

## 参数

- **subject**：一个与 `formatter` 兼容的 [doc://com.apple.documentation/documentation/ObjectiveC/NSObject-swift.class] 实例。

- **formatter**：一个能够将 `subject` 转换为字符串表示形式的 [doc://com.apple.documentation/documentation/Foundation/Formatter]。

## 讨论

使用此初始化程序创建一个文本视图，该视图使用 `formatter` 格式化 `subject`。

## 创建文本视图

- **init(_:tableName:bundle:comment:)**：创建一个文本视图，显示由键标识的本地化内容。

- **init(_:)**：创建一个文本视图，显示带样式的属性内容。

- **init(verbatim:)**：创建一个文本视图，显示未本地化的字符串字面量。

- **init(_:style:)**：创建一个实例，使用特定样式显示本地化的日期和时间。

- **init(_:format:)**：创建一个文本视图，显示由相应格式样式支持的非字符串类型的格式化表示。

- **init(timerInterval:pauseTime:countsDown:showsHours:)**：创建一个实例，显示指定时间间隔内的倒计时。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/init(_:formatter:)
crawled: 2025-12-02T21:48:18Z
---

# init(_:formatter:)

**Initializer**

Creates a text view that displays the formatted representation of a Foundation object.

## Declaration

```swift
init<Subject>(_ subject: Subject, formatter: Formatter) where Subject : NSObject
```

## Parameters

- **subject**: An [doc://com.apple.documentation/documentation/ObjectiveC/NSObject-swift.class] instance compatible with `formatter`.
- **formatter**: A [doc://com.apple.documentation/documentation/Foundation/Formatter] capable of converting `subject` into a string representation.

## Discussion

Use this initializer to create a text view that formats `subject` using `formatter`.

## Creating a text view

- **init(_:tableName:bundle:comment:)**: Creates a text view that displays localized content identified by a key.
- **init(_:)**: Creates a text view that displays styled attributed content.
- **init(verbatim:)**: Creates a text view that displays a string literal without localization.
- **init(_:style:)**: Creates an instance that displays localized dates and times using a specific style.
- **init(_:format:)**: Creates a text view that displays the formatted representation of a nonstring type supported by a corresponding format style.
- **init(timerInterval:pauseTime:countsDown:showsHours:)**: Creates an instance that displays a timer counting within the provided interval.

