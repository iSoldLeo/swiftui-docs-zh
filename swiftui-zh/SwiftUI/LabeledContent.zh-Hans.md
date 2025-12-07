---

来源：https://developer.apple.com/documentation/SwiftUI/LabeledContent
抓取时间：2025-12-02T17:27:20Z

---

# LabeledContent

**Structure**

用于将标签附加到包含值的视图的容器。

## 声明

```swift
struct LabeledContent<Label, Content>
```

## 概述

该实例的内容表示只读或读写值，其标签标识或描述该值的用途。生成的元素具有与其他框架控件一致的布局，并自动适应其容器，例如表单或工具栏。某些标签内容样式还会将样式或行为应用于值内容，例如使视图可选择。[Text](Text.zh-Hans.md)

以下示例将标签与自定义视图关联，并具有与标签匹配的布局：

```swift
Form {
    LabeledContent("Custom Value") {
        MyCustomView(value: $value)
    }
    Picker("Selected Value", selection: $selection) {
        Text("Option 1").tag(1)
        Text("Option 2").tag(2)
    }
}
```

### 自定义视图标签

您可以使用 [init(content:label:)](LabeledContent/init_content_label.zh-Hans.md) 初始化器，将带标签的内容与其标签对应的视图组合在一起。例如，您可以使用 [Text](Text.zh-Hans.md) 视图重写之前的标签内容示例：

```swift
LabeledContent {
    MyCustomView(value: $value)
} label: {
    Text("Custom Value")
}
```

`label` 视图构建器接受任何类型的视图，例如 [Label](Label.zh-Hans.md)：

```swift
LabeledContent {
    MyCustomView(value: $value)
} label: {
    Label("Custom Value", systemImage: "hammer")
}
```

如果需要为标签添加副标题，请使用视图构建器创建多个 `Text` 视图，其中第一个文本表示标题，第二个文本表示副标题：

```swift
LabeledContent {
    MyCustomView(value: $value)
} label: {
    Text("Custom Value")
    Text("Custom Subtitle Value")
}
```

### 文本标签内容

您可以使用字符串值或格式化值构建标签内容，以创建只读文本值显示：

```swift
Form {
    Section("Information") {
        LabeledContent("Name", value: person.name)
        LabeledContent("Age", value: person.age, format: .number)
        LabeledContent("Height", value: person.height,
            format: .measurement(width: .abbreviated))
    }
    if !person.pets.isEmpty {
        Section("Pets") {
            ForEach(pet) { pet in
                LabeledContent(pet.species, value: pet.name)
            }
        }
    }
}
```

SwiftUI 会尽可能使这些文本可选中。

### 组合元素

您可以将带标签的内容用作其他元素的标签。例如，[NavigationLink](NavigationLink.zh-Hans.md) 可以显示其链接目标的摘要值：

```swift
Form {
    NavigationLink(value: Settings.wifiDetail) {
        LabeledContent("Wi-Fi", value: ssidName)
    }
}
```

在某些情况下，用作值内容的视图的样式也经过特殊处理。例如，macOS 中嵌入式分组表单中的 [Toggle](Toggle.zh-Hans.md) 默认样式为开关，但当它用作外层 `LabeledContent` 实例中的值元素时，其样式为复选框：

```swift
Form {
    LabeledContent("Source Control") {
        Toggle("Refresh local status automatically",
            isOn: $refreshLocalStatus)
        Toggle("Fetch and refresh server status automatically",
            isOn: $refreshServerStatus)
        Toggle("Add and remove files automatically",
            isOn: $addAndRemoveFiles)
        Toggle("Select files to commit automatically",
            isOn: $selectFiles)
    }
}
```

### 控制标签可见性

标签用于传达值的标识或用途，这对于可访问性至关重要。但是，您可能希望在显示中隐藏标签，某些控件或上下文可能默认隐藏其标签。[labelsHidden()](View/labelsHidden.zh-Hans.md) 修饰符允许您控制此可见性。以下示例隐藏了两个标签，仅显示两个值视图的组合：

```swift
Group {
    LabeledContent("Custom Value") {
        MyCustomView(value: $value)
    }
    Picker("Selected Value", selection: $selection) {
        Text("Option 1").tag(1)
        Text("Option 2").tag(2)
    }
}
.labelsHidden()
```

### 设置标签内容样式

您可以使用 [labeledContentStyle(_:)](View/labeledContentStyle.zh-Hans.md) 修饰符设置标签样式。您还可以使用 [LabeledContentStyle](LabeledContentStyle.zh-Hans.md) 创建自定义样式。

## 创建标签内容

- **init(_:content:)**：创建一个标签视图，该视图的标签由本地化字符串键生成。

- **init(content:label:)**：创建一个标准标签元素，该元素包含一个显示元素值和标签的视图。

- **init(_:value:)**：创建一个标签信息视图。

- **init(_:value:format:)**：创建一个标签信息视图，该视图由格式化值生成。

- **init(_:)**：根据标签内容样式配置创建标签内容。

## 输入分组

- **Form**：用于分组数据输入控件的容器，例如设置或检查器中的控件。

- **formStyle(_:)**：设置视图层次结构中表单的样式。

- **labeledContentStyle(_:)**：设置标签内容的样式。

## 符合以下规范

- 可复制的

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/LabeledContent
crawled: 2025-12-02T17:27:20Z
---

# LabeledContent

**Structure**

A container for attaching a label to a value-bearing view.

## Declaration

```swift
struct LabeledContent<Label, Content>
```

## Overview

The instance’s content represents a read-only or read-write value, and its label identifies or describes the purpose of that value. The resulting element has a layout that’s consistent with other framework controls and automatically adapts to its container, like a form or toolbar. Some styles of labeled content also apply styling or behaviors to the value content, like making [Text](Text.zh-Hans.md) views selectable.

The following example associates a label with a custom view and has a layout that matches the label of the [Picker](Picker.zh-Hans.md):

```swift
Form {
    LabeledContent("Custom Value") {
        MyCustomView(value: $value)
    }
    Picker("Selected Value", selection: $selection) {
        Text("Option 1").tag(1)
        Text("Option 2").tag(2)
    }
}
```

### Custom view labels

You can assemble labeled content with an explicit view for its label using the [init(content:label:)](LabeledContent/init_content_label.zh-Hans.md) initializer. For example, you can rewrite the previous labeled content example using a [Text](Text.zh-Hans.md) view:

```swift
LabeledContent {
    MyCustomView(value: $value)
} label: {
    Text("Custom Value")
}
```

The `label` view builder accepts any kind of view, like a [Label](Label.zh-Hans.md):

```swift
LabeledContent {
    MyCustomView(value: $value)
} label: {
    Label("Custom Value", systemImage: "hammer")
}
```

For cases where adding a subtitle to the label is desired, use a view builder that creates multiple `Text` views where the first text represents the title and the second text represents the subtitle:

```swift
LabeledContent {
    MyCustomView(value: $value)
} label: {
    Text("Custom Value")
    Text("Custom Subtitle Value")
}
```

### Textual labeled content

You can construct labeled content with string values or formatted values to create read-only displays of textual values:

```swift
Form {
    Section("Information") {
        LabeledContent("Name", value: person.name)
        LabeledContent("Age", value: person.age, format: .number)
        LabeledContent("Height", value: person.height,
            format: .measurement(width: .abbreviated))
    }
    if !person.pets.isEmpty {
        Section("Pets") {
            ForEach(pet) { pet in
                LabeledContent(pet.species, value: pet.name)
            }
        }
    }
}
```

Wherever possible, SwiftUI makes this text selectable.

### Compositional elements

You can use labeled content as the label for other elements. For example, a [NavigationLink](NavigationLink.zh-Hans.md) can present a summary value for the destination it links to:

```swift
Form {
    NavigationLink(value: Settings.wifiDetail) {
        LabeledContent("Wi-Fi", value: ssidName)
    }
}
```

In some cases, the styling of views used as the value content is specialized as well. For example, while a [Toggle](Toggle.zh-Hans.md) in an inset group form on macOS is styled as a switch by default, it’s styled as a checkbox when used as a value element within a surrounding `LabeledContent` instance:

```swift
Form {
    LabeledContent("Source Control") {
        Toggle("Refresh local status automatically",
            isOn: $refreshLocalStatus)
        Toggle("Fetch and refresh server status automatically",
            isOn: $refreshServerStatus)
        Toggle("Add and remove files automatically",
            isOn: $addAndRemoveFiles)
        Toggle("Select files to commit automatically",
            isOn: $selectFiles)
    }
}
```

### Controlling label visibility

A label communicates the identity or purpose of the value, which is important for accessibility. However, you might want to hide the label in the display, and some controls or contexts may visually hide their label by default. The [labelsHidden()](View/labelsHidden.zh-Hans.md) modifier allows controlling that visibility. The following example hides both labels, producing only a group of the two value views:

```swift
Group {
    LabeledContent("Custom Value") {
        MyCustomView(value: $value)
    }
    Picker("Selected Value", selection: $selection) {
        Text("Option 1").tag(1)
        Text("Option 2").tag(2)
    }
}
.labelsHidden()
```

### Styling labeled content

You can set label styles using the [labeledContentStyle(_:)](View/labeledContentStyle.zh-Hans.md) modifier. You can also build custom styles using [LabeledContentStyle](LabeledContentStyle.zh-Hans.md).

## Creating labeled content

- **init(_:content:)**: Creates a labeled view that generates its label from a localized string key.
- **init(content:label:)**: Creates a standard labeled element, with a view that conveys the value of the element and a label.
- **init(_:value:)**: Creates a labeled informational view.
- **init(_:value:format:)**: Creates a labeled informational view from a formatted value.
- **init(_:)**: Creates labeled content based on a labeled content style configuration.

## Grouping inputs

- **Form**: A container for grouping controls used for data entry, such as in settings or inspectors.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **labeledContentStyle(_:)**: Sets a style for labeled content.

## Conforms To

- Copyable
- View

