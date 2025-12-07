--- 来源：https://developer.apple.com/documentation/SwiftUI/View/touchBarCustomizationLabel(_:)

抓取时间：2025-12-02T17:42:28Z

---

# touchBarCustomizationLabel(_:)

**实例方法**

设置一个用户可见的字符串，用于标识视图的功能。

## 声明

```swift
nonisolated func touchBarCustomizationLabel(_ label: Text) -> some View

```

## 参数

- **label**：一个包含自定义标签的视图。

## 返回值

一个设置了自定义标签的触控栏元素。

## 说明

此字符串在用户自定义期间可见。

```swift
TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar {
        Button("♥️", action: selectHearts)
            .touchBarCustomizationLabel(Text("Hearts"))
        Button("♣️", action: selectClubs)
            .touchBarCustomizationLabel(Text("Clubs"))
        Button("♠️", action: selectSpades)
            .touchBarCustomizationLabel(Text("Spades"))
        Button("♦️", action: selectDiamonds)
            .touchBarCustomizationLabel(Text("Diamonds"))
    }
```

## 管理触控栏输入

- **touchBar(content:)**：设置触控栏显示的内容。

- **touchBar(_:)**：设置触控栏在适用时显示的内容。

- **touchBarItemPrincipal(_:)**：设置对该触控栏具有特殊意义的主要视图。

- **touchBarItemPresence(_:)**：设置用户自定义视图的行为。

- **TouchBar**：用于在触控栏中显示的视图的容器。

- **TouchBarItemPresence**：影响用户自定义触控栏的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/touchBarCustomizationLabel(_:)
crawled: 2025-12-02T17:42:28Z
---

# touchBarCustomizationLabel(_:)

**Instance Method**

Sets a user-visible string that identifies the view’s functionality.

## Declaration

```swift
nonisolated func touchBarCustomizationLabel(_ label: Text) -> some View

```

## Parameters

- **label**: A `Text` view containing the customization label.

## Return Value

A Touch Bar element with a set customization label.

## Discussion

This string is visible during user customization.

```swift
TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar {
        Button("♥️", action: selectHearts)
            .touchBarCustomizationLabel(Text("Hearts"))
        Button("♣️", action: selectClubs)
            .touchBarCustomizationLabel(Text("Clubs"))
        Button("♠️", action: selectSpades)
            .touchBarCustomizationLabel(Text("Spades"))
        Button("♦️", action: selectDiamonds)
            .touchBarCustomizationLabel(Text("Diamonds"))
    }
```



## Managing Touch Bar input

- **touchBar(content:)**: Sets the content that the Touch Bar displays.
- **touchBar(_:)**: Sets the Touch Bar content to be shown in the Touch Bar when applicable.
- **touchBarItemPrincipal(_:)**: Sets principal views that have special significance to this Touch Bar.
- **touchBarItemPresence(_:)**: Sets the behavior of the user-customized view.
- **TouchBar**: A container for a view that you can show in the Touch Bar.
- **TouchBarItemPresence**: Options that affect user customization of the Touch Bar.

