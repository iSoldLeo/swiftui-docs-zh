--- 来源：https://developer.apple.com/documentation/SwiftUI/View/typeSelectEquivalent(_:)

抓取时间：2025-12-02T17:35:41Z

---

# typeSelectEquivalent(_:)

**实例方法**

在集合（例如列表或表格）中设置显式类型选择等效文本。

## 声明

```swift
nonisolated func typeSelectEquivalent(_ stringKey: LocalizedStringKey) -> some View

```

## 参数

- **stringKey**：要用作集合中视图类型选择等效文本的本地化字符串键。

## 说明

默认情况下，类型选择等效文本会自动从列表或表格中的任何 `Text` 或 `TextField` 内容派生而来。在下面的示例中，即使没有设置显式值，也可以使用类型选择来选择人员。

```swift
List(people, selection: $selectedPersonID) { person in
    Label {
        Text(person.name)
    } icon: {
        person.avatar
    }
}
```

当视图中没有文本内容，或者需要显示与视图中实际显示不同的值时，应显式设置类型选择值。显式值还能提高复杂视图类型的性能。在下面的示例中，显式设置了类型选择，以便选择原本只显示图像的视图。

```swift
List(people, selection: $selectedPersonID) { person in
    person.avatar
        .accessibilityLabel(person.name)
        .typeSelectEquivalent(person.name)
}
```

设置空字符串值会禁用视图的文本选择功能，而设置值 `nil` 则会使视图使用其默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/typeSelectEquivalent(_:)
crawled: 2025-12-02T17:35:41Z
---

# typeSelectEquivalent(_:)

**Instance Method**

Sets an explicit type select equivalent text in a collection, such as a list or table.

## Declaration

```swift
nonisolated func typeSelectEquivalent(_ stringKey: LocalizedStringKey) -> some View

```

## Parameters

- **stringKey**: The localized string key to use as a type select equivalent for a view in a collection.

## Discussion

By default, a type select equivalent is automatically derived from any `Text` or `TextField` content in a list or table. In the below example, type select can be used to select a person, even though no explicit value has been set.

```swift
List(people, selection: $selectedPersonID) { person in
    Label {
        Text(person.name)
    } icon: {
        person.avatar
    }
}
```

An explicit type select value should be set when there is no textual content or when a different value is desired compared to what’s displayed in the view. Explicit values also provide a more performant for complex view types. In the below example, type select is explicitly set to allow selection of views that otherwise only display an image.

```swift
List(people, selection: $selectedPersonID) { person in
    person.avatar
        .accessibilityLabel(person.name)
        .typeSelectEquivalent(person.name)
}
```

Setting an empty string value disables text selection for the view, and a value of `nil` results in the view using its default value.

