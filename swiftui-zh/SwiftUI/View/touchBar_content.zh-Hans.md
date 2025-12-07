--- 来源：https://developer.apple.com/documentation/SwiftUI/View/touchBar(content:)

抓取时间：2025-11-30T21:27:31Z

---

# touchBar(content:)

**实例方法**

设置触控栏显示的内容。

## 声明

```swift
nonisolated func touchBar<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## 参数

- **content**：触控栏要显示的视图集合。

## 返回值

包含触控栏内容的视图。

## 说明

当需要动态构建要在触控栏中显示的项目时，请使用 `touchBar(_:)`。触控栏会根据焦点状态适时显示内容。

在以下示例中，四个按钮被添加到触控栏内容结构体，然后添加到触控栏：

```swift
let touchBarItems = TouchBar(id: "myBarItems") {
    Button("♣️", action: {})
    Button("♥️", action: {})
    Button("♠️", action: {})
    Button("♦️", action: {})
}

TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar(touchBarItems)
```

## 管理触控栏输入

- **touchBar(_:)**：设置触控栏中显示的内容（如果适用）。

- **touchBarItemPrincipal(_:)**：设置对该触控栏具有特殊意义的主要视图。

- **touchBarCustomizationLabel(_:)**：设置一个用户可见的字符串，用于标识视图的功能。

- **touchBarItemPresence(_:)**：设置用户自定义视图的行为。

- **TouchBar**：一个用于在触控栏中显示的视图容器。

- **TouchBarItemPresence**：影响用户自定义触控栏的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/touchBar(content:)
crawled: 2025-11-30T21:27:31Z
---

# touchBar(content:)

**Instance Method**

Sets the content that the Touch Bar displays.

## Declaration

```swift
nonisolated func touchBar<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## Parameters

- **content**: A collection of views to be displayed by the Touch Bar.

## Return Value

A view that contains the Touch Bar content.

## Discussion

Use `touchBar(_:)` when you need to dynamically construct items to show in the Touch Bar. The content is displayed by the Touch Bar when appropriate, depending on focus.

In the example below, four buttons are added to a Touch Bar content struct and then added to the Touch Bar:

```swift
let touchBarItems = TouchBar(id: "myBarItems") {
    Button("♣️", action: {})
    Button("♥️", action: {})
    Button("♠️", action: {})
    Button("♦️", action: {})
}

TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar(touchBarItems)
```



## Managing Touch Bar input

- **touchBar(_:)**: Sets the Touch Bar content to be shown in the Touch Bar when applicable.
- **touchBarItemPrincipal(_:)**: Sets principal views that have special significance to this Touch Bar.
- **touchBarCustomizationLabel(_:)**: Sets a user-visible string that identifies the view’s functionality.
- **touchBarItemPresence(_:)**: Sets the behavior of the user-customized view.
- **TouchBar**: A container for a view that you can show in the Touch Bar.
- **TouchBarItemPresence**: Options that affect user customization of the Touch Bar.

