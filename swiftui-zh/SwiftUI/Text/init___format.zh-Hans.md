--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/init(_:format:)

抓取时间：2025-12-01T02:39:08Z

---

# init(_:format:)

**Initializer**

创建一个文本视图，用于显示由相应格式样式支持的非字符串类型的格式化表示。

## 声明

```swift
init<F>(_ input: F.FormatInput, format: F) where F : FormatStyle, F.FormatInput : Equatable, F.FormatOutput == AttributedString
```

## 参数

- **input**：要显示的底层值。

- **format**：类型为 `F` 的格式样式，用于将类型为 `F.FormatInput` 的底层值转换为带属性的字符串表示。

## 讨论

使用此初始化器创建由非字符串值支持的文本视图，并使用 [doc://com.apple.documentation/documentation/Foundation/FormatStyle] 将类型转换为属性字符串表示形式。对该值的任何更改都会更新文本视图显示的字符串。

在以下示例中，三个 [Text](../Text.zh-Hans.md) 视图通过使用不同的 [doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle] 选项，以不同的日期和时间字段组合显示日期。

```swift
@State private var myDate = Date()
var body: some View {
    VStack {
        Text(myDate, format: Date.FormatStyle(date: .numeric, time: .omitted).attributedStyle)
        Text(myDate, format: Date.FormatStyle(date: .complete, time: .complete).attributedStyle)
        Text(myDate, format: Date.FormatStyle().hour(.defaultDigitsNoAMPM).minute().attributedStyle)
    }
}
```

## 创建文本视图

- **init(_:tableName:bundle:comment:)**：创建一个显示由键标识的本地化内容的文本视图。

- **init(_:)**：创建一个显示样式化属性内容的文本视图。

- **init(verbatim:)**：创建一个显示未本地化的字符串字面量的文本视图。

- **init(_:style:)**：创建一个实例，使用特定样式显示本地化的日期和时间。

- **init(_:formatter:)**：创建一个文本视图，显示 Foundation 对象的格式化表示形式。

- **init(timerInterval:pauseTime:countsDown:showsHours:)**：创建一个实例，显示指定时间间隔内的计时器。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/init(_:format:)
crawled: 2025-12-01T02:39:08Z
---

# init(_:format:)

**Initializer**

Creates a text view that displays the formatted representation of a nonstring type supported by a corresponding format style.

## Declaration

```swift
init<F>(_ input: F.FormatInput, format: F) where F : FormatStyle, F.FormatInput : Equatable, F.FormatOutput == AttributedString
```

## Parameters

- **input**: The underlying value to display.
- **format**: A format style of type `F` to convert the underlying value of type `F.FormatInput` to an attributed string representation.

## Discussion

Use this initializer to create a text view backed by a nonstring value, using a [doc://com.apple.documentation/documentation/Foundation/FormatStyle] to convert the type to an attributed string representation. Any changes to the value update the string displayed by the text view.

In the following example, three [Text](../Text.zh-Hans.md) views present a date with different combinations of date and time fields, by using different [doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle] options.

```swift
@State private var myDate = Date()
var body: some View {
    VStack {
        Text(myDate, format: Date.FormatStyle(date: .numeric, time: .omitted).attributedStyle)
        Text(myDate, format: Date.FormatStyle(date: .complete, time: .complete).attributedStyle)
        Text(myDate, format: Date.FormatStyle().hour(.defaultDigitsNoAMPM).minute().attributedStyle)
    }
}
```



## Creating a text view

- **init(_:tableName:bundle:comment:)**: Creates a text view that displays localized content identified by a key.
- **init(_:)**: Creates a text view that displays styled attributed content.
- **init(verbatim:)**: Creates a text view that displays a string literal without localization.
- **init(_:style:)**: Creates an instance that displays localized dates and times using a specific style.
- **init(_:formatter:)**: Creates a text view that displays the formatted representation of a Foundation object.
- **init(timerInterval:pauseTime:countsDown:showsHours:)**: Creates an instance that displays a timer counting within the provided interval.

