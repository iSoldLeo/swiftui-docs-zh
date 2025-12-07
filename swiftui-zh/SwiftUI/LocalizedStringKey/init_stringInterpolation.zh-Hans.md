--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/init(stringInterpolation:)

抓取时间：2025-12-03T06:19:41Z

---

# init(stringInterpolation:)

**Initializer**

根据给定的字符串插值创建本地化字符串键。

## 声明

```swift
init(stringInterpolation: LocalizedStringKey.StringInterpolation)
```

## 参数

- **stringInterpolation**：用作本地化键的字符串插值。

## 说明

要根据字符串插值创建本地化字符串键，请使用 `\()` 字符串插值语法。 Swift 会将表达式中的参数类型与 [StringInterpolation](StringInterpolation.zh-Hans.md) 中的 `appendInterpolation` 方法之一进行匹配。插值类型可以包括数值、Foundation 类型以及 SwiftUI [Text](../Text.zh-Hans.md) 和 [Image](../Image.zh-Hans.md) 实例。

以下示例使用字符串插值，并带有两个参数：一个未标记的 [doc://com.apple.documentation/documentation/Foundation/Date] 和一个带有标记的 `style` 的 [DateStyle](../Text/DateStyle.zh-Hans.md)。编译器会将这些参数映射到 [appendInterpolation(_:style:)](StringInterpolation/appendInterpolation___style.zh-Hans.md) 方法，并以此构建用于创建 [LocalizedStringKey](../LocalizedStringKey.zh-Hans.md) 的字符串。

```swift
let key = LocalizedStringKey("Date is \(company.foundedDate, style: .offset)")
let text = Text(key) // Text contains "Date is +45 years"
```

您可以更简洁地编写此示例，隐式地创建一个 [LocalizedStringKey](../LocalizedStringKey.zh-Hans.md) 作为 [Text](../Text.zh-Hans.md) 初始化器的参数：

```swift
let text = Text("Date is \(company.foundedDate, style: .offset)")
```

## 从插值创建键

- **LocalizedStringKey.StringInterpolation**：在构建字符串字面量时，使用插值表示其内容，用于创建本地化字符串键。


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/init(stringInterpolation:)
crawled: 2025-12-03T06:19:41Z
---

# init(stringInterpolation:)

**Initializer**

Creates a localized string key from the given string interpolation.

## Declaration

```swift
init(stringInterpolation: LocalizedStringKey.StringInterpolation)
```

## Parameters

- **stringInterpolation**: The string interpolation to use as the localization key.

## Discussion

To create a localized string key from a string interpolation, use the `\()` string interpolation syntax. Swift matches the parameter types in the expression to one of the `appendInterpolation` methods in [StringInterpolation](StringInterpolation.zh-Hans.md). The interpolated types can include numeric values, Foundation types, and SwiftUI [Text](../Text.zh-Hans.md) and [Image](../Image.zh-Hans.md) instances.

The following example uses a string interpolation with two arguments: an unlabeled [doc://com.apple.documentation/documentation/Foundation/Date] and a [DateStyle](../Text/DateStyle.zh-Hans.md) labeled `style`. The compiler maps these to the method [appendInterpolation(_:style:)](StringInterpolation/appendInterpolation___style.zh-Hans.md) as it builds the string that it creates the [LocalizedStringKey](../LocalizedStringKey.zh-Hans.md) with.

```swift
let key = LocalizedStringKey("Date is \(company.foundedDate, style: .offset)")
let text = Text(key) // Text contains "Date is +45 years"
```

You can write this example more concisely, implicitly creating a [LocalizedStringKey](../LocalizedStringKey.zh-Hans.md) as the parameter to the [Text](../Text.zh-Hans.md) initializer:

```swift
let text = Text("Date is \(company.foundedDate, style: .offset)")
```

## Creating a key from an interpolation

- **LocalizedStringKey.StringInterpolation**: Represents the contents of a string literal with interpolations while it’s being built, for use in creating a localized string key.

