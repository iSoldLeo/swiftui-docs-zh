--- 来源：https://developer.apple.com/documentation/SwiftUI/View/modifierKeyAlternate(_:_:)

抓取时间：2025-12-02T17:41:46Z

---

# modifierKeyAlternate(_:_:)

**实例方法**

构建一个视图，当用户按下指定组合的修饰键时，该视图将替换当前修改后的视图。

## 声明

```swift
nonisolated func modifierKeyAlternate<V>(_ modifiers: EventModifiers, @ViewBuilder _ alternate: () -> V) -> some View where V : View

```

## 参数

- **modifiers**：要与备用视图关联的修饰键。当所有这些键都被按下时，SwiftUI 会将当前修改后的视图替换为该备用视图。

- **alternate**：用于在按下匹配的修饰键时构建当前修改后视图的备用视图的视图构建器。

## 返回值

一个修改后的视图，其中包含一个备用视图，用于在按下特定修饰键时显示。

## 讨论

```swift
Button("Go Forward", ...)
    .modifierKeyAlternate(.option) {
        Button("Go to Page…", ...)
    }
```

在菜单样式上下文中，修饰键备用视图会成为备用菜单项。如果修改后的视图有键盘快捷键，则会以此为基础生成备用视图的快捷键。

```swift
// File > Save
Button("Save", ...) // ⌘ S
    .keyboardShortcut("s")
    .modifierKeyAlternate(.option) {
        Button("Save All", ...) // ⌥⌘ S
    }
```

要为备用视图使用不同的键盘快捷键，请在视图构建器中显式添加一个。SwiftUI 将使用您显式指定的快捷键，而不是它自动推断的快捷键。

```swift
Button("Go Forward", ...) // ⌘ →
    .keyboardShortcut(.rightArrow)
    .modifierKeyAlternate(.control) {
        Button("Go To Page…", ...) // ⌃ →
            .keyboardShortcut(.rightArrow, modifiers: .control)
    }
```

一个视图可以有多个修饰键备用视图，前提是它们关联的修饰键不同。当多个备用视图与当前按下的键匹配时，将使用最匹配的那个。

```swift
Button("Save", ...) // ⌘ S
    .keyboardShortcut("s")
    .modifierKeyAlternate(.option) {
        Button("Save All", ...) // ⌥⌘ S
    }
    .modifierKeyAlternate([.option, .shift]) {
        Button("Save a Copy…", ...) // ⇧⌥⌘ S
    }
```

## 响应修饰键

- **onModifierKeysChanged(mask:initial:_:)**：当用户按下或松开硬件修饰键时，执行相应的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/modifierKeyAlternate(_:_:)
crawled: 2025-12-02T17:41:46Z
---

# modifierKeyAlternate(_:_:)

**Instance Method**

Builds a view to use in place of the modified view when the user presses the modifier key(s) indicated by the given set.

## Declaration

```swift
nonisolated func modifierKeyAlternate<V>(_ modifiers: EventModifiers, @ViewBuilder _ alternate: () -> V) -> some View where V : View

```

## Parameters

- **modifiers**: The modifier keys to associate with the alternate view. While all these keys are held, SwiftUI will replace the modified view with this alternate one.
- **alternate**: A view builder for constructing the modified view’s alternate when matching modifier keys are pressed.

## Return Value

A modified view with an alternate view to use while specific modifier keys are held down.

## Discussion

```swift
Button("Go Forward", ...)
    .modifierKeyAlternate(.option) {
        Button("Go to Page…", ...)
    }
```

In menu style contexts, modifier key alternates become alternate menu items. If the modified view has a keyboard shortcut, it will be used as the basis for the alternate view’s shortcut.

```swift
// File > Save
Button("Save", ...) // ⌘ S
    .keyboardShortcut("s")
    .modifierKeyAlternate(.option) {
        Button("Save All", ...) // ⌥⌘ S
    }
```

To use a different keyboard shortcut for the alternate view, add one explicitly in the view builder. SwiftUI will use your explicit shortcut instead of its own inferred one.

```swift
Button("Go Forward", ...) // ⌘ →
    .keyboardShortcut(.rightArrow)
    .modifierKeyAlternate(.control) {
        Button("Go To Page…", ...) // ⌃ →
            .keyboardShortcut(.rightArrow, modifiers: .control)
    }
```

A view can have multiple modifier key alternates, provided their associated modifier keys are different. When multiple alternates match the currently-held keys, the most specific match prevails.

```swift
Button("Save", ...) // ⌘ S
    .keyboardShortcut("s")
    .modifierKeyAlternate(.option) {
        Button("Save All", ...) // ⌥⌘ S
    }
    .modifierKeyAlternate([.option, .shift]) {
        Button("Save a Copy…", ...) // ⇧⌥⌘ S
    }
```

## Responding to modifier keys

- **onModifierKeysChanged(mask:initial:_:)**: Performs an action whenever the user presses or releases a hardware modifier key.

