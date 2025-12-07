---
来源： https://developer.apple.com/documentation/SwiftUI/TouchBarItemPresence
抓取时间： 2025-12-02T17:42:30Z
---

# TouchBarItemPresence

**Enumeration**

影响用户自定义触摸栏的选项。

## 声明

```swift
enum TouchBarItemPresence
```

## 获取存在选项

- **TouchBarItemPresence.default(_:)**：默认情况下触摸栏视图是可见的，但可以在自定义时移除。
- **TouchBarItemPresence.optional(_:)**：触摸栏视图默认不可见，但会出现在自定义调板中。
- **TouchBarItemPresence.required(_:)**：默认情况下触摸栏视图可见，且在自定义过程中无法移除。

## 管理触摸栏输入

- **touchBar(content:)**：设置触摸栏显示的内容。
- **touchBar(_:)**: 设置触摸栏显示的内容：设置 Touch Bar 中要显示的内容（如适用）。
- **touchBarItemPrincipal(_:)**：设置对该触摸栏有特殊意义的主要视图。
- **touchBarCustomizationLabel(_:)**：设置用户可见的字符串，用于标识视图的功能。
- **touchBarItemPresence(_:)**：设置用户自定义视图的行为。
- **TouchBar**：设置用户自定义视图的行为：可在触摸栏中显示的视图容器。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/TouchBarItemPresence
crawled: 2025-12-02T17:42:30Z
---

# TouchBarItemPresence

**Enumeration**

Options that affect user customization of the Touch Bar.

## Declaration

```swift
enum TouchBarItemPresence
```

## Getting presence options

- **TouchBarItemPresence.default(_:)**: The Touch Bar view is visible by default, but can be removed during customization.
- **TouchBarItemPresence.optional(_:)**: The Touch Bar view isn’t visible by default, but appears in the customization palette.
- **TouchBarItemPresence.required(_:)**: The Touch Bar view is visible by default and cannot be removed during customization.

## Managing Touch Bar input

- **touchBar(content:)**: Sets the content that the Touch Bar displays.
- **touchBar(_:)**: Sets the Touch Bar content to be shown in the Touch Bar when applicable.
- **touchBarItemPrincipal(_:)**: Sets principal views that have special significance to this Touch Bar.
- **touchBarCustomizationLabel(_:)**: Sets a user-visible string that identifies the view’s functionality.
- **touchBarItemPresence(_:)**: Sets the behavior of the user-customized view.
- **TouchBar**: A container for a view that you can show in the Touch Bar.

## Conforms To

- Sendable
- SendableMetatype

