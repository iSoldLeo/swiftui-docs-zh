--- 来源：https://developer.apple.com/documentation/SwiftUI/View/touchBarItemPresence(_:)

抓取时间：2025-11-30T21:27:34Z

---

# touchBarItemPresence(_:)

**实例方法**

设置用户自定义视图的行为。

## 声明

```swift
nonisolated func touchBarItemPresence(_ presence: TouchBarItemPresence) -> some View

```

## 参数

- **presence**：允许的 [TouchBarItemPresence](../TouchBarItemPresence.zh-Hans.md) 描述之一。

## 返回值

描述此触控栏视图行为的特征。

## 说明

使用 `touchBarItemPresence(_:)` 定义用户自定义期间特定触控栏视图的可见性要求。

触控栏视图可能如下：

- `.required`：用户不允许移除。

- `.default`：默认显示，用户自定义前显示，但可移除。

- `.optional`：默认不可见，但可通过自定义面板添加。

每个 [TouchBarItemPresence](../TouchBarItemPresence.zh-Hans.md) 都必须使用一个字符串进行初始化，该字符串是此项目的全局唯一标识符。

在下面的示例中，除“俱乐部”项目外，所有触控栏项目默认都可见。“俱乐部”项目设置为 `.optional`，但可由用户配置：

```swift
TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar {
        Button("♥️", action: selectHearts)
            .touchBarItemPresence(.required("heartsKey"))
        Button("♣️", action: selectClubs)
            .touchBarItemPresence(.optional("clubsKey"))
        Button("♠️", action: selectSpades)
            .touchBarItemPresence(.required("spadesKey"))
        Button("♦️", action: selectDiamonds)
            .touchBarItemPresence(.required("diamondsKey"))
}
```

## 管理触控栏输入

- **touchBar(content:)**：设置触控栏显示的内容。

- **touchBar(_:)**：设置触控栏中显示的内容（如适用）。

- **touchBarItemPrincipal(_:)**：设置对该触控栏具有特殊意义的主要视图。

- **touchBarCustomizationLabel(_:)**：设置一个用户可见的字符串，用于标识视图的功能。

- **TouchBar**：一个用于在触控栏中显示的视图容器。

- **TouchBarItemPresence**：影响用户自定义触控栏的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/touchBarItemPresence(_:)
crawled: 2025-11-30T21:27:34Z
---

# touchBarItemPresence(_:)

**Instance Method**

Sets the behavior of the user-customized view.

## Declaration

```swift
nonisolated func touchBarItemPresence(_ presence: TouchBarItemPresence) -> some View

```

## Parameters

- **presence**: One of the allowed [TouchBarItemPresence](../TouchBarItemPresence.zh-Hans.md) descriptions.

## Return Value

A trait that describes the behavior for this Touch Bar view.

## Discussion

Use `touchBarItemPresence(_:)` to define the visibility requirements of a particular Touch Bar view during customization by the user.

Touch Bar views may be:

- `.required`: not allowed to be removed by the user.
- `.default`: shown by default prior to user customization, but removable.
- `.optional`: not visible by default, but can be added through the customization palette.

Each [TouchBarItemPresence](../TouchBarItemPresence.zh-Hans.md) must be initialized with a string that is a globally unique identifier for this item.

In the example below, all of the Touch Bar items are visible in the Touch Bar by default, except for the “Clubs” item. It’s set to `.optional` but is configurable by the user:

```swift
TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar {
        Button("♥️", action: selectHearts)
            .touchBarItemPresence(.required("heartsKey"))
        Button("♣️", action: selectClubs)
            .touchBarItemPresence(.optional("clubsKey"))
        Button("♠️", action: selectSpades)
            .touchBarItemPresence(.required("spadesKey"))
        Button("♦️", action: selectDiamonds)
            .touchBarItemPresence(.required("diamondsKey"))
}
```



## Managing Touch Bar input

- **touchBar(content:)**: Sets the content that the Touch Bar displays.
- **touchBar(_:)**: Sets the Touch Bar content to be shown in the Touch Bar when applicable.
- **touchBarItemPrincipal(_:)**: Sets principal views that have special significance to this Touch Bar.
- **touchBarCustomizationLabel(_:)**: Sets a user-visible string that identifies the view’s functionality.
- **TouchBar**: A container for a view that you can show in the Touch Bar.
- **TouchBarItemPresence**: Options that affect user customization of the Touch Bar.

