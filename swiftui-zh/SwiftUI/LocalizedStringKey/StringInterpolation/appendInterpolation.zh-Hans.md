--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:)

抓取时间：2025-12-04T13:21:48Z

---

# appendInterpolation(_:)

**实例方法**

将一个带属性的字符串追加到字符串插值中。

## 声明

```swift
mutating func appendInterpolation(_ attributedString: AttributedString)
```

## 参数

- **attributedString**：要追加的带属性的字符串。

## 说明

不要直接调用此方法；编译器在解释字符串插值时会使用它。

以下示例展示了如何使用字符串插值来格式化 [doc://com.apple.documentation/documentation/Foundation/AttributedString] 并将其追加到静态文本中。由此产生的插值会隐式地创建一个 [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md)，[Text](../../Text.zh-Hans.md) 视图会使用该 [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md) 来提供其内容。

```swift
struct ContentView: View {

    var nextDate: AttributedString {
        var result = Calendar.current
            .nextWeekend(startingAfter: Date.now)!
            .start
            .formatted(
                .dateTime
                .month(.wide)
                .day()
                .attributed
            )
        result.backgroundColor = .green
        result.foregroundColor = .white
        return result
    }

    var body: some View {
        Text("Our next catch-up is on \(nextDate)!")
    }
}
```

在本例中，假设应用程序运行在设置为俄语语言环境的设备上，并且在俄语本地化的 `Localizable.strings` 文件中包含以下条目：

```swift
"Our next catch-up is on %@!" = "Наша следующая встреча состоится %@!";
```

当 [Text](../../Text.zh-Hans.md) 视图渲染其内容时，带属性的字符串 `nextDate` 会替换格式说明符 `%@`，并保留其颜色和日期格式属性：

## 向插值追加内容

- **appendInterpolation(_:specifier:)**：将可转换为带有格式说明符的字符串的类型追加到字符串插值中。

- **appendInterpolation(_:format:)**：将支持相应格式样式的非字符串类型的格式化表示形式附加到字符串中。

- **appendInterpolation(_:formatter:)**：将 Objective-C 子类的可选格式化实例附加到字符串插值中。

- **appendInterpolation(_:style:)**：将格式化的日期附加到字符串插值中。

- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**：将计时器间隔附加到字符串插值中。

- **appendLiteral(_:)**：附加字符串字面量。


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:)
crawled: 2025-12-04T13:21:48Z
---

# appendInterpolation(_:)

**Instance Method**

Appends an attributed string to a string interpolation.

## Declaration

```swift
mutating func appendInterpolation(_ attributedString: AttributedString)
```

## Parameters

- **attributedString**: The attributed string to append.

## Discussion

Don’t call this method directly; it’s used by the compiler when interpreting string interpolations.

The following example shows how to use a string interpolation to format an [doc://com.apple.documentation/documentation/Foundation/AttributedString] and append it to static text. The resulting interpolation implicitly creates a [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md), which a [Text](../../Text.zh-Hans.md) view uses to provide its content.

```swift
struct ContentView: View {

    var nextDate: AttributedString {
        var result = Calendar.current
            .nextWeekend(startingAfter: Date.now)!
            .start
            .formatted(
                .dateTime
                .month(.wide)
                .day()
                .attributed
            )
        result.backgroundColor = .green
        result.foregroundColor = .white
        return result
    }

    var body: some View {
        Text("Our next catch-up is on \(nextDate)!")
    }
}
```

For this example, assume that the app runs on a device set to a Russian locale, and has the following entry in a Russian-localized `Localizable.strings` file:

```swift
"Our next catch-up is on %@!" = "Наша следующая встреча состоится %@!";
```

The attributed string `nextDate` replaces the format specifier `%@`,  maintaining its color and date-formatting attributes, when the [Text](../../Text.zh-Hans.md) view renders its contents:



## Appending to an interpolation

- **appendInterpolation(_:specifier:)**: Appends a type, convertible to a string with a format specifier, to a string interpolation.
- **appendInterpolation(_:format:)**: Appends the formatted representation  of a nonstring type supported by a corresponding format style.
- **appendInterpolation(_:formatter:)**: Appends an optionally-formatted instance of an Objective-C subclass to a string interpolation.
- **appendInterpolation(_:style:)**: Appends a formatted date to a string interpolation.
- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**: Appends a timer interval to a string interpolation.
- **appendLiteral(_:)**: Appends a literal string.

