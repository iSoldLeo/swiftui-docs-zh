--- 来源：https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(_:value:)

抓取时间：2025-12-01T10:31:36Z

---

# init(_:value:)

**Initializer**

创建一个带标签的信息视图。

## 声明

```swift
init<S1, S2>(_ title: S1, value: S2) where S1 : StringProtocol, S2 : StringProtocol
```

## 参数

- **title**：描述视图用途的字符串。

- **value**：要添加标签的值。

## 说明

此初始化器会为您创建一个 [Text](../Text.zh-Hans.md) 标签，并将标题的处理方式与 [init(_:)](../Text/init.zh-Hans.md) 类似。有关字符串本地化的更多信息，请参阅 `Text`。

```swift
Form {
    ForEach(person.pet) { pet in
        LabeledContent(pet.species, value: pet.name)
    }
}
```

## 创建带标签的内容

- **init(_:content:)**：创建一个带标签的视图，该视图的标签由本地化的字符串键生成。

- **init(content:label:)**：创建一个标准的带标签元素，该元素包含一个视图，用于显示元素的值和标签。

- **init(_:value:format:)**：根据格式化的值创建带标签的信息视图。

- **init(_:)**：根据带标签的内容样式配置创建带标签的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(_:value:)
crawled: 2025-12-01T10:31:36Z
---

# init(_:value:)

**Initializer**

Creates a labeled informational view.

## Declaration

```swift
init<S1, S2>(_ title: S1, value: S2) where S1 : StringProtocol, S2 : StringProtocol
```

## Parameters

- **title**: A string that describes the purpose of the view.
- **value**: The value being labeled.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) label on your behalf, and treats the title similar to [init(_:)](../Text/init.zh-Hans.md). See `Text` for more information about localizing strings.

```swift
Form {
    ForEach(person.pet) { pet in
        LabeledContent(pet.species, value: pet.name)
    }
}
```

## Creating labeled content

- **init(_:content:)**: Creates a labeled view that generates its label from a localized string key.
- **init(content:label:)**: Creates a standard labeled element, with a view that conveys the value of the element and a label.
- **init(_:value:format:)**: Creates a labeled informational view from a formatted value.
- **init(_:)**: Creates labeled content based on a labeled content style configuration.

