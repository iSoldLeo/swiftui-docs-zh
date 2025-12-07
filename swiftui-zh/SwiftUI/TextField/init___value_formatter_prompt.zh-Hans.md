---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(_:value:formatter:prompt:)
抓取时间： 2025-11-30T21:36:36Z


# init(_:value:formatter:prompt:)

**Initializer**

创建一个文本字段，对绑定值应用格式化器，标签由标题字符串生成。

### 声明

```swift
nonisolated init<S, V>(_ title: S, value: Binding<V>, formatter: Formatter, prompt: Text?) where S : StringProtocol
```

## 参数

- **title**：文本字段的标题，描述其用途。
- **value**：要编辑的基本值。
- **formatter**：在用户编辑的字符串与`V` 类型的基础值之间进行转换时使用的格式化格式。如果`formatter` 不能执行转换，则文本字段不会修改`binding.value`。
- **prompt**：`Text`，指导用户在文本字段中输入内容。

### 讨论

使用该初始化程序可创建一个与绑定值绑定的文本字段，并使用[doc://com.apple.documentation/documentation/Foundation/Formatter] 转换为该类型。对绑定值的更改会更新文本字段显示的字符串。只要格式样式可以解析文本，编辑文本字段就会更新绑定值。如果格式样式无法解析输入内容，则绑定值保持不变。

使用[onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) 修改器可在用户提交此文本字段时调用一个操作。

下面的示例使用[doc://com.apple.documentation/documentation/Swift/Double] 作为绑定值，并使用[doc://com.apple.documentation/documentation/Foundation/NumberFormatter] 实例来转换字符串。格式器使用[doc://com.apple.documentation/documentation/Foundation/NumberFormatter/Style/decimal] 样式，允许输入小数部分。当用户输入时，绑定值会更新，反过来又会更新使用不同格式样式的三个[Text](../Text.zh-Hans.md) 视图。如果用户输入的文本不代表有效的`Double`，则绑定值不会更新。

```swift
@State private var label = "Double"
@State private var myDouble: Double = 0.673
@State private var numberFormatter: NumberFormatter = {
    var nf = NumberFormatter()
    nf.numberStyle = .decimal
    return nf
}()

var body: some View {
    VStack {
        TextField(
            label,
            value: $myDouble,
            formatter: numberFormatter
        )
        Text(myDouble, format: .number)
        Text(myDouble, format: .number.precision(.significantDigits(5)))
        Text(myDouble, format: .number.notation(.scientific))
    }
}
```

## 创建带值的文本字段

- **init(_:value:format:prompt:)**：创建一个文本字段，对绑定值应用格式样式，标签由本地化标题字符串生成。
- **init(value:format:prompt:label:)**：创建一个文本字段，为绑定值应用格式样式，标签由视图创建器生成。
- **init(_:value:formatter:)**：创建一个绑定任意类型的实例，`V`。
- **init(value:formatter:prompt:label:)**：创建一个文本字段，将格式化器应用于绑定的可选值，标签由视图创建器生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(_:value:formatter:prompt:)
crawled: 2025-11-30T21:36:36Z
---

# init(_:value:formatter:prompt:)

**Initializer**

Creates a text field that applies a formatter to a bound value, with a label generated from a title string.

## Declaration

```swift
nonisolated init<S, V>(_ title: S, value: Binding<V>, formatter: Formatter, prompt: Text?) where S : StringProtocol
```

## Parameters

- **title**: The title of the text field, describing its purpose.
- **value**: The underlying value to edit.
- **formatter**: A formatter to use when converting between the string the user edits and the underlying value of type `V`. If `formatter` can’t perform the conversion, the text field doesn’t modify `binding.value`.
- **prompt**: A `Text` which provides users with guidance on what to enter into the text field.

## Discussion

Use this initializer to create a text field that binds to a bound value, using a [doc://com.apple.documentation/documentation/Foundation/Formatter] to convert to and from this type. Changes to the bound value update the string displayed by the text field. Editing the text field updates the bound value, as long as the formatter can parse the text. If the format style can’t parse the input, the bound value remains unchanged.

Use the [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) modifier to invoke an action whenever the user submits this text field.

The following example uses a [doc://com.apple.documentation/documentation/Swift/Double] as the bound value, and a [doc://com.apple.documentation/documentation/Foundation/NumberFormatter] instance to convert to and from a string representation. The formatter uses the [doc://com.apple.documentation/documentation/Foundation/NumberFormatter/Style/decimal] style, to allow entering a fractional part. As the user types, the bound value updates, which in turn updates three [Text](../Text.zh-Hans.md) views that use different format styles. If the user enters text that doesn’t represent a valid `Double`, the bound value doesn’t update.

```swift
@State private var label = "Double"
@State private var myDouble: Double = 0.673
@State private var numberFormatter: NumberFormatter = {
    var nf = NumberFormatter()
    nf.numberStyle = .decimal
    return nf
}()

var body: some View {
    VStack {
        TextField(
            label,
            value: $myDouble,
            formatter: numberFormatter
        )
        Text(myDouble, format: .number)
        Text(myDouble, format: .number.precision(.significantDigits(5)))
        Text(myDouble, format: .number.notation(.scientific))
    }
}
```

## Creating a text field with a value

- **init(_:value:format:prompt:)**: Creates a text field that applies a format style to a bound value, with a label generated from a localized title string.
- **init(value:format:prompt:label:)**: Creates a text field that applies a format style to a bound value, with a label generated from a view builder.
- **init(_:value:formatter:)**: Create an instance which binds over an arbitrary type, `V`.
- **init(value:formatter:prompt:label:)**: Creates a text field that applies a formatter to a bound optional value, with a label generated from a view builder.

