--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusSection()

抓取时间：2025-11-30T21:28:16Z

---

# focusSection()

**实例方法**

指示应使用视图的框架及其可聚焦子视图来引导焦点移动。

## 声明

```swift
nonisolated func focusSection() -> some View

```

## 返回值

一个可以引导焦点到其可聚焦子视图的视图。

## 讨论

使用焦点分区可以自定义用户在视图之间移动焦点时 SwiftUI 的行为。

以下 tvOS 示例在屏幕左上角放置了三个按钮（“1”、“2”和“3”），在右下角放置了三个按钮（“A”、“B”和“C”）。默认情况下，在 Siri Remote 上向右滑动“1”到“3”组中的任何按钮都不会有任何反应，因为焦点系统在其右侧找不到任何可聚焦的视图。但是，通过将包含“A”到“C”按钮的 [VStack](../VStack.zh-Hans.md) 声明为焦点区域，[VStack](../VStack.zh-Hans.md) 就可以接收焦点，并将焦点传递给其第一个可聚焦的子视图（“A”按钮）。示例中在 [VStack](../VStack.zh-Hans.md) 上添加了边框，以说明这种空间布局。

```swift
var body: some View {
    HStack {
        VStack {
            Button ("1") {}
            Button ("2") {}
            Button ("3") {}
            Spacer()
        }
        .border(Color.white, width: 2)

        Spacer()
        VStack {
            Spacer()
            Button ("A") {}
            Button ("B") {}
            Button ("C") {}
        }
        .border(Color.white, width: 2)
        .focusSection()
    }
}
```

请注意，由于包含“1”到“3”按钮的 [VStack](../VStack.zh-Hans.md) 没有将自身声明为焦点区域，因此无法将焦点从“A”到“C”按钮向左重定向。这些按钮的左侧都没有可聚焦的视图——在本例中，既没有按钮，也没有带有 `focusSection()` 修饰符的 [VStack](../VStack.zh-Hans.md)。

将此修饰符应用于视图会根据移动方式影响其焦点行为：

- **方向性移动**：使用 Siri Remote 手势、键盘上的方向键或任何其他以基本方向（上、下、左、右）为单位的输入方式进行导航都会产生方向性移动。当使用 `focusSection()` 进行修饰时，视图的框架将能够接收焦点，并将其指向移动方向上最近的可聚焦子项。在前面的示例中，将右侧的 [VStack](../VStack.zh-Hans.md) 声明为焦点区域，使其能够接收来自左侧按钮的向右焦点。

- **顺序移动**：使用数码表冠、键盘上的 Tab 键或任何其他以顺序方式移动的输入方式进行导航，都会产生顺序移动。当您使用 `focusSection()` 修饰符时，SwiftUI 会偏离其默认的基于布局的顺序，先访问被修改视图的每个可聚焦子视图，然后再恢复默认顺序。在这些可聚焦子视图中，SwiftUI 会继续按照布局顺序（从前到后，从上到下）访问视图。

`focusSection()` 不会影响被修改视图的可聚焦性。如果被修改视图没有可聚焦子视图，则此修饰符无效。

## 设置焦点范围

- **focusScope(_:)**：创建一个焦点范围，SwiftUI 使用该范围来限制默认的焦点偏好。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusSection()
crawled: 2025-11-30T21:28:16Z
---

# focusSection()

**Instance Method**

Indicates that the view’s frame and cohort of focusable descendants should be used to guide focus movement.

## Declaration

```swift
nonisolated func focusSection() -> some View

```

## Return Value

A view that can guide focus to its focusable descendents.

## Discussion

Use focus sections to customize SwiftUI’s behavior when the user moves focus between views.

The following tvOS example places three buttons (“1”, “2”, and “3”) at the upper left of the screen and three buttons (“A”, “B”, and “C”) at the bottom right. By default, swiping right on the Siri Remote on any of the buttons in the “1” - “3” group would do nothing, since the focus system finds no focusable views directly to their right. But by declaring the [VStack](../VStack.zh-Hans.md) that encloses buttons “A” - “C” as a focus section, the [VStack](../VStack.zh-Hans.md) can receive focus, and deliver that focus to its first focusable child (button “A”). The example puts a border on the [VStack](../VStack.zh-Hans.md) to illustrate this spatial arrangement.

```swift
var body: some View {
    HStack {
        VStack {
            Button ("1") {}
            Button ("2") {}
            Button ("3") {}
            Spacer()
        }
        .border(Color.white, width: 2)

        Spacer()
        VStack {
            Spacer()
            Button ("A") {}
            Button ("B") {}
            Button ("C") {}
        }
        .border(Color.white, width: 2)
        .focusSection()
    }
}
```



Note that because the [VStack](../VStack.zh-Hans.md) containing buttons “1” - “3” does not declare itself as a focus section, it is impossible to direct focus back to the left from buttons “A” - “C”. None of those buttons has a focusable view — in this case either a button or a [VStack](../VStack.zh-Hans.md) with the `focusSection()` modifier — directly to its left.

Applying this modifier to a view affects focus behavior based on the style of movement:

- **Directional movement**: Navigating with Siri Remote gestures, arrow keys on a keyboard, or any other type of input that works in terms of cardinal directions (up, down, left, right) produces directional movement. When modified with `focusSection()`, the view’s frame becomes capable of accepting focus in order to direct it at its nearest focusable descendant in the direction of travel. In the earlier example, declaring the right-side [VStack](../VStack.zh-Hans.md) as a focus section allowed it to receive right-directed focus from the buttons on the left.
- **Sequential movement**: Navigating with a Digital Crown, the Tab key on a keyboard, or any other type of input that works in terms of the next or previous item in a sequence, produces sequential movement. When you use the `focusSection()` modifier, SwiftUI deviates from its default layout-based sequence to visit each of the modified view’s focusable descendants before resuming the default sequence. Within the set of focusable descendants, SwiftUI continues to visit views in layout order (leading-to-trailing, top-to-bottom).

`focusSection()` does not affect the focusability of the modified view. If the modified view has no focusable descendants, then the modifier does nothing.

## Setting focus scope

- **focusScope(_:)**: Creates a focus scope that SwiftUI uses to limit default focus preferences.

