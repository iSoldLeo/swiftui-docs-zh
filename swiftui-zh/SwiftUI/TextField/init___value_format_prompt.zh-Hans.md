---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(_:value:format:prompt:)
抓取时间：2025-11-30T21:36:34Z


# init(_:value:format:prompt:)

**Initializer**

创建一个文本字段，对绑定值应用格式样式，标签由本地化标题字符串生成。

### 声明

```swift
nonisolated init<F>(_ titleKey: LocalizedStringKey, value: Binding<F.FormatInput>, format: F, prompt: Text? = nil) where F : ParseableFormatStyle, F.FormatOutput == String
```

## 参数

- **titleKey**：文本字段的标题，描述其用途。
- **value**：要编辑的基本值。
- **format**：`F`类型的格式样式，用于在用户编辑的字符串和`F.FormatInput`类型的底层值之间进行转换。如果`format` 不能执行转换，文本字段将保留`binding.value` 不变。如果用户在无效状态下停止编辑文本，文本字段会将字段文本更新为最后已知的有效值。
- **prompt**：`Text`，可指导用户在文本字段中输入什么内容。

### 讨论

使用此初始化程序可创建一个与绑定值绑定的文本字段，并使用[doc://com.apple.documentation/documentation/Foundation/ParseableFormatStyle] 转换为该类型。对绑定值的更改会更新文本字段显示的字符串。只要格式样式可以解析文本，编辑文本字段就会更新绑定值。如果格式样式无法解析输入内容，则绑定值保持不变。

使用[onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) 修改器可在用户提交此文本字段时调用一个操作。

下面的示例使用[doc://com.apple.documentation/documentation/Swift/Double] 作为绑定值，并使用[doc://com.apple.documentation/documentation/Foundation/FloatingPointFormatStyle] 实例来转换字符串。当用户键入时，绑定值会更新，这反过来又会更新三个使用不同格式样式的[Text](../Text.zh-Hans.md) 视图。如果用户输入的文本不代表有效的`Double`，则绑定值不会更新。

```swift
@State private var myDouble: Double = 0.673
var body: some View {
    VStack {
        TextField(
            "Double",
            value: $myDouble,
            format: .number
        )
        Text(myDouble, format: .number)
        Text(myDouble, format: .number.precision(.significantDigits(5)))
        Text(myDouble, format: .number.notation(.scientific))
    }
}
```



## 创建带值的文本字段

- **init(value:format:prompt:label:)**：创建一个文本字段，将格式样式应用于绑定的值，标签由视图创建器生成。
- **init(_:value:formatter:)**：创建一个绑定任意类型的实例，`V`。
- **init(_:value:formatter:prompt:)**：创建一个文本字段，将格式化器应用于绑定值，标签由标题字符串生成。
- **init(value:formatter:prompt:label:)**：**init(value:formatter:prompt:label:)**： 创建一个文本字段，该字段可为绑定的可选值应用格式，其标签由视图创建器生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(_:value:format:prompt:)
crawled: 2025-11-30T21:36:34Z
---

# init(_:value:format:prompt:)

**Initializer**

Creates a text field that applies a format style to a bound value, with a label generated from a localized title string.

## Declaration

```swift
nonisolated init<F>(_ titleKey: LocalizedStringKey, value: Binding<F.FormatInput>, format: F, prompt: Text? = nil) where F : ParseableFormatStyle, F.FormatOutput == String
```

## Parameters

- **titleKey**: The title of the text field, describing its purpose.
- **value**: The underlying value to edit.
- **format**: A format style of type `F` to use when converting between the string the user edits and the underlying value of type `F.FormatInput`. If `format` can’t perform the conversion, the text field leaves `binding.value` unchanged. If the user stops editing the text in an invalid state, the text field updates the field’s text to the last known valid value.
- **prompt**: A `Text` which provides users with guidance on what to type into the text field.

## Discussion

Use this initializer to create a text field that binds to a bound value, using a [doc://com.apple.documentation/documentation/Foundation/ParseableFormatStyle] to convert to and from this type. Changes to the bound value update the string displayed by the text field. Editing the text field updates the bound value, as long as the format style can parse the text. If the format style can’t parse the input, the bound value remains unchanged.

Use the [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) modifier to invoke an action whenever the user submits this text field.

The following example uses a [doc://com.apple.documentation/documentation/Swift/Double] as the bound value, and a [doc://com.apple.documentation/documentation/Foundation/FloatingPointFormatStyle] instance to convert to and from a string representation. As the user types, the bound value updates, which in turn updates three [Text](../Text.zh-Hans.md) views that use different format styles. If the user enters text that doesn’t represent a valid `Double`, the bound value doesn’t update.

```swift
@State private var myDouble: Double = 0.673
var body: some View {
    VStack {
        TextField(
            "Double",
            value: $myDouble,
            format: .number
        )
        Text(myDouble, format: .number)
        Text(myDouble, format: .number.precision(.significantDigits(5)))
        Text(myDouble, format: .number.notation(.scientific))
    }
}
```



## Creating a text field with a value

- **init(value:format:prompt:label:)**: Creates a text field that applies a format style to a bound value, with a label generated from a view builder.
- **init(_:value:formatter:)**: Create an instance which binds over an arbitrary type, `V`.
- **init(_:value:formatter:prompt:)**: Creates a text field that applies a formatter to a bound value, with a label generated from a title string.
- **init(value:formatter:prompt:label:)**: Creates a text field that applies a formatter to a bound optional value, with a label generated from a view builder.

