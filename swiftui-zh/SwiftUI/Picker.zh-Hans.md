--- 来源：https://developer.apple.com/documentation/SwiftUI/Picker
抓取时间：2025-12-02T16:24:20Z

---

# 选择器

**Structure**

用于从一组互斥值中进行选择的控件。

## 声明

```swift
struct Picker<Label, SelectionValue, Content> where Label : View, SelectionValue : Hashable, Content : View
```

## 概述

您可以通过提供选择绑定、标签和选择器要显示的内容来创建选择器。将 `selection` 参数设置为绑定属性，该属性提供要显示为当前选择的值。将标签设置为一个视图，该视图以视觉方式描述在选择器中选择内容的目的，然后提供选择器要显示的内容。

例如，假设有一个冰淇淋口味枚举，以及一个用于保存所选口味的变量 [State](State.zh-Hans.md)：

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate
```

您可以通过提供标签、与当前选择的绑定以及用于存放选择器内容的视图集合来创建一个选择器，以便从这些值中进行选择。使用 `View/tag(_:)` 视图修饰符为每个内容视图添加一个标签，使每个选择的类型与绑定的状态变量的类型匹配：

```swift
List {
    Picker("Flavor", selection: $selectedFlavor) {
        Text("Chocolate").tag(Flavor.chocolate)
        Text("Vanilla").tag(Flavor.vanilla)
        Text("Strawberry").tag(Flavor.strawberry)
    }
}
```

如果您像上面的示例一样为选择器提供一个字符串标签，则选择器会使用该标签初始化一个 [Text](Text.zh-Hans.md) 视图作为标签。或者，您可以使用 [init(selection:content:label:)](Picker/init_selection_content_label.zh-Hans.md) 初始化器从其他视图中组合标签。选择器的具体外观取决于上下文。如果在 iOS 中使用 [List](List.zh-Hans.md) 中的选择器，它会显示在一行中，包含标签和选定值，以及一个箭头指示您可以点击该行来选择新值：

如果需要为标签添加副标题，可以使用视图构建器创建多个 `Text` 视图，其中第一个文本表示标题，第二个文本表示副标题：

```swift
List {
    Picker(selection: $selectedFlavor) {
        Text("Chocolate").tag(Flavor.chocolate)
        Text("Vanilla").tag(Flavor.vanilla)
        Text("Strawberry").tag(Flavor.strawberry)
    } label: {
        Text("Flavor")
        Text("Choose your favorite flavor")
    }
}
```

### 遍历选择器的选项

要为 `Picker` 提供选择值而无需显式列出每个选项，您可以使用 [ForEach](ForEach.zh-Hans.md) 创建选择器：

```swift
Picker("Flavor", selection: $selectedFlavor) {
    ForEach(Flavor.allCases) { flavor in
        Text(flavor.rawValue.capitalized)
    }
}
```

[ForEach](ForEach.zh-Hans.md) 会自动使用每个选项的 `id` 为选择视图分配标签。这是因为 `Flavor` 符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 协议。

上面的示例依赖于 `Flavor` 将其 `id` 参数的类型定义为与选择类型完全匹配。如果并非如此，则需要覆盖标签。例如，考虑一个 `Topping` 类型以及每种口味的建议配料：

```swift
enum Topping: String, CaseIterable, Identifiable {
    case nuts, cookies, blueberries
    var id: Self { self }
}

extension Flavor {
    var suggestedTopping: Topping {
        switch self {
        case .chocolate: return .nuts
        case .vanilla: return .cookies
        case .strawberry: return .blueberries
        }
    }
}

@State private var suggestedTopping: Topping = .nuts
```

以下示例显示了一个绑定到 `Topping` 类型的选择器，而所有选项均为 `Flavor` 实例。每个选项都使用标签修饰符将建议的配料与其显示的口味关联起来：

```swift
List {
    Picker("Flavor", selection: $suggestedTopping) {
        ForEach(Flavor.allCases) { flavor in
            Text(flavor.rawValue.capitalized)
                .tag(flavor.suggestedTopping)
        }
    }
    HStack {
        Text("Suggested Topping")
        Spacer()
        Text(suggestedTopping.rawValue.capitalized)
            .foregroundStyle(.secondary)
    }
}
```

当用户选择巧克力时，选择器会将 `suggestedTopping` 设置为关联标签中的值：

选择器 [ForEach](ForEach.zh-Hans.md) 中的视图需要显式标签修饰符的另一个示例是，当您使用除 `Self` 之外的任何值作为 `id` 参数类型来选择符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 协议的枚举的子集时。例如，字符串枚举可能使用子集的字符串 `rawValue` 作为 `id`。该标识符类型与选择类型（即枚举本身的类型）不匹配。

### 选择器样式

您可以使用符合 [PickerStyle](PickerStyle.zh-Hans.md) 协议的样式（例如 [segmented](PickerStyle/segmented.zh-Hans.md) 或 [menu](PickerStyle/menu.zh-Hans.md)）自定义选择器的外观和交互方式。要为视图中的所有选择器实例设置特定样式，请使用 [pickerStyle(_:)](View/pickerStyle.zh-Hans.md) 修饰符。以下示例将 [segmented](PickerStyle/segmented.zh-Hans.md) 样式应用于两个分别用于选择口味和配料的选择器：

```swift
VStack {
    Picker("Flavor", selection: $selectedFlavor) {
        ForEach(Flavor.allCases) { flavor in
            Text(flavor.rawValue.capitalized)
        }
    }
    Picker("Topping", selection: $selectedTopping) {
        ForEach(Topping.allCases) { topping in
            Text(topping.rawValue.capitalized)
        }
    }
}
.pickerStyle(.segmented)
```

## 创建选择器

- **init(_:selection:content:)**：创建一个选择器，该选择器根据本地化字符串键生成标签。

- **init(selection:content:label:)**：创建一个显示自定义标签的选择器。

## 为集合创建选择器

- **init(_:sources:selection:content:)**：创建一个绑定到集合的选择器，该选择器根据字符串生成标签。

- **init(sources:selection:content:label:)**：创建一个显示自定义标签的选择器。

## 创建带有图像标签的选择器

- **init(_:image:selection:content:)**：创建一个选择器，该选择器根据本地化字符串键和图像资源生成标签。

- **init(_:image:sources:selection:content:)**：创建一个绑定到集合的选择器，该选择器根据字符串和图像资源生成标签。

- **init(_:systemImage:selection:content:)**：创建一个选择器，该选择器根据本地化字符串键和系统图像生成标签。

- **init(_:systemImage:sources:selection:content:)**：创建一个绑定到集合的选择器，该选择器根据字符串生成标签。

## 已弃用的初始化器

- **init(selection:label:content:)**：创建一个显示自定义标签的选择器。

## 初始化器

- **init(_:image:selection:content:currentValueLabel:)**：创建一个选择器，该选择器接受自定义的当前值标签，并根据本地化的字符串键和图像资源生成标签。

- **init(_:image:sources:selection:content:currentValueLabel:)**：创建一个绑定到绑定集合的选择器，该选择器接受自定义的当前值标签，并根据字符串和图像资源生成标签。

- **init(_:selection:content:currentValueLabel:)**：创建一个选择器，该选择器根据本地化的字符串键生成标签，并接受自定义的当前值标签。

- **init(_:sources:selection:content:currentValueLabel:)**：创建一个绑定到绑定集合的选择器，该选择器根据字符串生成标签，并接受自定义的当前值标签。

- **init(_:systemImage:selection:content:currentValueLabel:)**：创建一个选择器，该选择器接受自定义的当前值标签，并根据本地化的字符串键和系统图像生成标签。

- **init(_:systemImage:sources:selection:content:currentValueLabel:)**：创建一个绑定到绑定集合的选择器，该选择器接受自定义的当前值标签，并根据字符串生成标签。

- **init(selection:content:label:currentValueLabel:)**：创建一个选择器，该选择器在适用情况下显示自定义标签和自定义值标签。

- **init(sources:selection:content:label:currentValueLabel:)**：创建一个选择器，该选择器在适用情况下显示自定义标签和当前值标签。

## 从一组选项中进行选择

- **pickerStyle(_:)**：设置此视图中选择器的样式。

- **horizontalRadioGroupLayout()**：设置此视图中单选按钮组样式选择器的样式，使其水平排列，单选按钮位于布局内。

- **defaultWheelPickerItemHeight(_:)**：设置默认的轮盘式选择器项目高度。

- **defaultWheelPickerItemHeight**：轮盘式选择器（例如日期选择器）中项目的默认高度。

- **paletteSelectionEffect(_:)**：指定应用于调色板项目的选择效果。

- **PaletteSelectionEffect**：应用于调色板项目的选择效果。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/Picker
crawled: 2025-12-02T16:24:20Z
---

# Picker

**Structure**

A control for selecting from a set of mutually exclusive values.

## Declaration

```swift
struct Picker<Label, SelectionValue, Content> where Label : View, SelectionValue : Hashable, Content : View
```

## Overview

You create a picker by providing a selection binding, a label, and the content for the picker to display. Set the `selection` parameter to a bound property that provides the value to display as the current selection. Set the label to a view that visually describes the purpose of selecting content in the picker, and then provide the content for the picker to display.

For example, consider an enumeration of ice cream flavors and a [State](State.zh-Hans.md) variable to hold the selected flavor:

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate
```

You can create a picker to select among the values by providing a label, a binding to the current selection, and a collection of views for the picker’s content. Append a tag to each of these content views using the `View/tag(_:)` view modifier so that the type of each selection matches the type of the bound state variable:

```swift
List {
    Picker("Flavor", selection: $selectedFlavor) {
        Text("Chocolate").tag(Flavor.chocolate)
        Text("Vanilla").tag(Flavor.vanilla)
        Text("Strawberry").tag(Flavor.strawberry)
    }
}
```

If you provide a string label for the picker, as the example above does, the picker uses it to initialize a [Text](Text.zh-Hans.md) view as a label. Alternatively, you can use the [init(selection:content:label:)](Picker/init_selection_content_label.zh-Hans.md) initializer to compose the label from other views. The exact appearance of the picker depends on the context. If you use a picker in a [List](List.zh-Hans.md) in iOS, it appears in a row with the label and selected value, and a chevron to indicate that you can tap the row to select a new value:



For cases where adding a subtitle to the label is desired, use a view builder that creates multiple `Text` views where the first text represents the title and the second text represents the subtitle:

```swift
List {
    Picker(selection: $selectedFlavor) {
        Text("Chocolate").tag(Flavor.chocolate)
        Text("Vanilla").tag(Flavor.vanilla)
        Text("Strawberry").tag(Flavor.strawberry)
    } label: {
        Text("Flavor")
        Text("Choose your favorite flavor")
    }
}
```

### Iterating over a picker’s options

To provide selection values for the `Picker` without explicitly listing each option, you can create the picker with a [ForEach](ForEach.zh-Hans.md):

```swift
Picker("Flavor", selection: $selectedFlavor) {
    ForEach(Flavor.allCases) { flavor in
        Text(flavor.rawValue.capitalized)
    }
}
```

[ForEach](ForEach.zh-Hans.md) automatically assigns a tag to the selection views using each option’s `id`. This is possible because `Flavor` conforms to the [doc://com.apple.documentation/documentation/Swift/Identifiable] protocol.

The example above relies on the fact that `Flavor` defines the type of its `id` parameter to exactly match the selection type. If that’s not the case, you need to override the tag. For example, consider a `Topping` type and a suggested topping for each flavor:

```swift
enum Topping: String, CaseIterable, Identifiable {
    case nuts, cookies, blueberries
    var id: Self { self }
}

extension Flavor {
    var suggestedTopping: Topping {
        switch self {
        case .chocolate: return .nuts
        case .vanilla: return .cookies
        case .strawberry: return .blueberries
        }
    }
}

@State private var suggestedTopping: Topping = .nuts
```

The following example shows a picker that’s bound to a `Topping` type, while the options are all `Flavor` instances. Each option uses the tag modifier to associate the suggested topping with the flavor it displays:

```swift
List {
    Picker("Flavor", selection: $suggestedTopping) {
        ForEach(Flavor.allCases) { flavor in
            Text(flavor.rawValue.capitalized)
                .tag(flavor.suggestedTopping)
        }
    }
    HStack {
        Text("Suggested Topping")
        Spacer()
        Text(suggestedTopping.rawValue.capitalized)
            .foregroundStyle(.secondary)
    }
}
```

When the user selects chocolate, the picker sets `suggestedTopping` to the value in the associated tag:



Another example of when the views in a picker’s [ForEach](ForEach.zh-Hans.md) need an explicit tag modifier is when you select over the cases of an enumeration that conforms to the [doc://com.apple.documentation/documentation/Swift/Identifiable] protocol by using anything besides `Self` as the `id` parameter type. For example, a string enumeration might use the case’s `rawValue` string as the `id`. That identifier type doesn’t match the selection type, which is the type of the enumeration itself.

### Styling pickers

You can customize the appearance and interaction of pickers using styles that conform to the [PickerStyle](PickerStyle.zh-Hans.md) protocol, like [segmented](PickerStyle/segmented.zh-Hans.md) or [menu](PickerStyle/menu.zh-Hans.md). To set a specific style for all picker instances within a view, use the [pickerStyle(_:)](View/pickerStyle.zh-Hans.md) modifier. The following example applies the [segmented](PickerStyle/segmented.zh-Hans.md) style to two pickers that independently select a flavor and a topping:

```swift
VStack {
    Picker("Flavor", selection: $selectedFlavor) {
        ForEach(Flavor.allCases) { flavor in
            Text(flavor.rawValue.capitalized)
        }
    }
    Picker("Topping", selection: $selectedTopping) {
        ForEach(Topping.allCases) { topping in
            Text(topping.rawValue.capitalized)
        }
    }
}
.pickerStyle(.segmented)
```



## Creating a picker

- **init(_:selection:content:)**: Creates a picker that generates its label from a localized string key.
- **init(selection:content:label:)**: Creates a picker that displays a custom label.

## Creating a picker for a collection

- **init(_:sources:selection:content:)**: Creates a picker bound to a collection of bindings that generates its label from a string.
- **init(sources:selection:content:label:)**: Creates a picker that displays a custom label.

## Creating a picker with an image label

- **init(_:image:selection:content:)**: Creates a picker that generates its label from a localized string key and image resource
- **init(_:image:sources:selection:content:)**: Creates a picker bound to a collection of bindings that generates its label from a string and image resource.
- **init(_:systemImage:selection:content:)**: Creates a picker that generates its label from a localized string key and system image.
- **init(_:systemImage:sources:selection:content:)**: Creates a picker bound to a collection of bindings that generates its label from a string.

## Deprecated initializers

- **init(selection:label:content:)**: Creates a picker that displays a custom label.

## Initializers

- **init(_:image:selection:content:currentValueLabel:)**: Creates a picker that accepts a custom current value label and generates its label from a localized string key and image resource
- **init(_:image:sources:selection:content:currentValueLabel:)**: Creates a picker bound to a collection of bindings that accepts a custom current value label and generates its label from a string and image resource.
- **init(_:selection:content:currentValueLabel:)**: Creates a picker that generates its label from a localized string key and accepts a custom current value label.
- **init(_:sources:selection:content:currentValueLabel:)**: Creates a picker bound to a collection of bindings that generates its label from a string and accepts a custom current value label.
- **init(_:systemImage:selection:content:currentValueLabel:)**: Creates a picker that accepts a custom current value label and generates its label from a localized string key and system image.
- **init(_:systemImage:sources:selection:content:currentValueLabel:)**: Creates a picker bound to a collection of bindings that accepts a custom current value label and generates its label from a string.
- **init(selection:content:label:currentValueLabel:)**: Creates a picker that displays a custom label and a custom value label where applicable.
- **init(sources:selection:content:label:currentValueLabel:)**: Creates a picker that displays a custom label and current value label where applicable.

## Choosing from a set of options

- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **horizontalRadioGroupLayout()**: Sets the style for radio group style pickers within this view to be horizontally positioned with the radio buttons inside the layout.
- **defaultWheelPickerItemHeight(_:)**: Sets the default wheel-style picker item height.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **paletteSelectionEffect(_:)**: Specifies the selection effect to apply to a palette item.
- **PaletteSelectionEffect**: The selection effect to apply to a palette item.

## Conforms To

- View

