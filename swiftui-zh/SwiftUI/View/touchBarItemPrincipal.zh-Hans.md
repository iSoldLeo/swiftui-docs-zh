--- 来源：https://developer.apple.com/documentation/SwiftUI/View/touchBarItemPrincipal(_:)

抓取时间：2025-12-02T17:42:27Z

---

# touchBarItemPrincipal(_:)

**实例方法**

设置对当前触控栏具有特殊意义的主要视图。

## 声明

```swift
nonisolated func touchBarItemPrincipal(_ principal: Bool = true) -> some View

```

## 参数

- **principal**：一个布尔值，指示是否将此视图在触控栏中突出显示，与其他视图进行比较。

## 返回值

一个触控栏视图，其中包含一个位于触控栏行中心的元素。

## 说明

使用 `touchBarItemPrincipal(_:)` 将视图指定为触控栏中的重要视图。目前，该视图将位于行的中心。

以下示例将最后一个按钮设置为触控栏视图的主按钮。

```swift
let touchBarItems = TouchBar(id: "myBarItems") {
    Button("♣️", action: {})
    Button("♥️", action: {})
    Button("♠️", action: {})
    Button("♦️", action: {})
       .touchBarItemPrincipal(true)
}

TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar(touchBarItems)
```

## 管理触控栏输入

- **touchBar(content:)**：设置触控栏显示的内容。

- **touchBar(_:)**：设置触控栏中显示的内容（如适用）。

- **touchBarCustomizationLabel(_:)**：设置一个用户可见的字符串，用于标识视图的功能。

- **touchBarItemPresence(_:)**：设置用户自定义视图的行为。

- **TouchBar**：用于在触控栏中显示的视图的容器。

- **TouchBarItemPresence**：影响用户自定义触控栏的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/touchBarItemPrincipal(_:)
crawled: 2025-12-02T17:42:27Z
---

# touchBarItemPrincipal(_:)

**Instance Method**

Sets principal views that have special significance to this Touch Bar.

## Declaration

```swift
nonisolated func touchBarItemPrincipal(_ principal: Bool = true) -> some View

```

## Parameters

- **principal**: A Boolean value that indicates whether to display this view prominently in the Touch Bar compared to other views.

## Return Value

A Touch Bar view with one element centered in the Touch Bar row.

## Discussion

Use `touchBarItemPrincipal(_:)` to designate a view as a significant view in the Touch Bar. Currently, that view will be placed in the center of the row.

The example below sets the last button as the principal button for the Touch Bar view.

```swift
let touchBarItems = TouchBar(id: "myBarItems") {
    Button("♣️", action: {})
    Button("♥️", action: {})
    Button("♠️", action: {})
    Button("♦️", action: {})
       .touchBarItemPrincipal(true)
}

TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar(touchBarItems)
```





## Managing Touch Bar input

- **touchBar(content:)**: Sets the content that the Touch Bar displays.
- **touchBar(_:)**: Sets the Touch Bar content to be shown in the Touch Bar when applicable.
- **touchBarCustomizationLabel(_:)**: Sets a user-visible string that identifies the view’s functionality.
- **touchBarItemPresence(_:)**: Sets the behavior of the user-customized view.
- **TouchBar**: A container for a view that you can show in the Touch Bar.
- **TouchBarItemPresence**: Options that affect user customization of the Touch Bar.

