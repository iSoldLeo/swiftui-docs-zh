---
来源： https://developer.apple.com/documentation/SwiftUI/TouchBar
抓取时间： 2025-12-02T17:42:29Z
---

# TouchBar

**Structure**

用于在触摸栏中显示视图的容器。

## 声明

```swift
struct TouchBar<Content> where Content : View
```

## 创建触摸栏视图

- **init(content:)**：创建一个不可定制的触摸栏视图容器。
- **init(id:content:)**：创建具有全局唯一标识符的可定制触摸栏视图容器。

## 管理触摸栏输入

- **touchBar(content:)**：设置触摸栏显示的内容。
- **touchBar(_:)**: 设置触摸栏显示的内容：设置 Touch Bar 中要显示的内容（如适用）。
- **touchBarItemPrincipal(_:)**：设置对该触摸栏有特殊意义的主要视图。
- **touchBarCustomizationLabel(_:)**：设置用户可见的字符串，用于标识视图的功能。
- **touchBarItemPresence(_:)**：设置用户自定义视图的行为。
- **TouchBarItemPresence**：影响用户自定义触摸栏的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/TouchBar
crawled: 2025-12-02T17:42:29Z
---

# TouchBar

**Structure**

A container for a view that you can show in the Touch Bar.

## Declaration

```swift
struct TouchBar<Content> where Content : View
```

## Creating a Touch Bar view

- **init(content:)**: Creates a non-customizable Touch Bar view container.
- **init(id:content:)**: Creates a customizable Touch Bar view container with a globally unique identifier.

## Managing Touch Bar input

- **touchBar(content:)**: Sets the content that the Touch Bar displays.
- **touchBar(_:)**: Sets the Touch Bar content to be shown in the Touch Bar when applicable.
- **touchBarItemPrincipal(_:)**: Sets principal views that have special significance to this Touch Bar.
- **touchBarCustomizationLabel(_:)**: Sets a user-visible string that identifies the view’s functionality.
- **touchBarItemPresence(_:)**: Sets the behavior of the user-customized view.
- **TouchBarItemPresence**: Options that affect user customization of the Touch Bar.

