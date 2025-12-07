--- 来源：https://developer.apple.com/documentation/SwiftUI/View/touchBar(_:)

抓取时间：2025-12-02T17:42:27Z

---

# touchBar(_:)

**实例方法**

设置触控栏在适用时显示的内容。

## 声明

```swift
nonisolated func touchBar<Content>(_ touchBar: TouchBar<Content>) -> some View where Content : View

```

## 参数

- **touchBar**：触控栏显示的视图集合。

## 返回值

包含触控栏内容的视图。

## 说明

使用 [touchBar(_:)](touchBar.zh-Hans.md) 提供一组静态视图，这些视图会在适当的时候由触控栏显示，具体取决于视图是否具有焦点。

以下示例提供了触控栏内联内容，用于创建触控栏显示的内容：

```swift
func selectHearts() {/* ... */ }
func selectClubs() { /* ... */ }
func selectSpades() { /* ... */ }
func selectDiamonds() { /* ... */ }

TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar {
        Button("♥️ - Hearts", action: selectHearts)
        Button("♣️ - Clubs", action: selectClubs)
        Button("♠️ - Spades", action: selectSpades)
        Button("♦️ - Diamonds", action: selectDiamonds)
    }
```

## 管理触控栏输入

- **touchBar(content:)**：设置触控栏显示的内容。

- **touchBarItemPrincipal(_:)**：设置对该触控栏具有特殊意义的主要视图。

- **touchBarCustomizationLabel(_:)**：设置一个用户可见的字符串，用于标识视图的功能。

- **touchBarItemPresence(_:)**：设置用户自定义视图的行为。

- **TouchBar**：用于在触控栏中显示的视图的容器。

- **TouchBarItemPresence**：影响用户自定义触控栏的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/touchBar(_:)
crawled: 2025-12-02T17:42:27Z
---

# touchBar(_:)

**Instance Method**

Sets the Touch Bar content to be shown in the Touch Bar when applicable.

## Declaration

```swift
nonisolated func touchBar<Content>(_ touchBar: TouchBar<Content>) -> some View where Content : View

```

## Parameters

- **touchBar**: A collection of views that the Touch Bar displays.

## Return Value

A view that contains the Touch Bar content.

## Discussion

Use [touchBar(_:)](touchBar.zh-Hans.md) to provide a static set of views that are displayed by the Touch Bar when appropriate, depending on whether the view has focus.

The example below provides Touch Bar content in-line, that creates the content the Touch Bar displays:

```swift
func selectHearts() {/* ... */ }
func selectClubs() { /* ... */ }
func selectSpades() { /* ... */ }
func selectDiamonds() { /* ... */ }

TextField("TouchBar Demo", text: $placeholder)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
    .focusable()
    .touchBar {
        Button("♥️ - Hearts", action: selectHearts)
        Button("♣️ - Clubs", action: selectClubs)
        Button("♠️ - Spades", action: selectSpades)
        Button("♦️ - Diamonds", action: selectDiamonds)
    }
```



## Managing Touch Bar input

- **touchBar(content:)**: Sets the content that the Touch Bar displays.
- **touchBarItemPrincipal(_:)**: Sets principal views that have special significance to this Touch Bar.
- **touchBarCustomizationLabel(_:)**: Sets a user-visible string that identifies the view’s functionality.
- **touchBarItemPresence(_:)**: Sets the behavior of the user-customized view.
- **TouchBar**: A container for a view that you can show in the Touch Bar.
- **TouchBarItemPresence**: Options that affect user customization of the Touch Bar.

