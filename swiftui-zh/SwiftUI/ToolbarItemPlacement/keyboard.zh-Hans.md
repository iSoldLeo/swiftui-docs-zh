---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/keyboard
抓取时间： 2025-12-03T06:03:12Z
---

# 键盘

**类型属性**

项目放在键盘部分。

## 声明

```swift
static let keyboard: ToolbarItemPlacement
```

## 讨论

在 iOS 系统中，键盘项目出现时位于软件键盘上方，安装了硬件键盘时则位于屏幕底部。

在 macOS 上，键盘项目将置于触摸栏内。

可以使用`FocusedValue`根据当前聚焦的视图调整键盘栏的内容。在下面的示例中，只有当相应的`TextField` 被聚焦时，键盘栏才会获得额外的按钮。

```swift
enum Field {
    case suit
    case rank
}

struct KeyboardBarDemo : View {
    @FocusedValue(\.field) var field: Field?

    var body: some View {
        HStack {
            TextField("Suit", text: $suitText)
                .focusedValue(\.field, .suit)
            TextField("Rank", text: $rankText)
                .focusedValue(\.field, .rank)
        }
        .toolbar {
            ToolbarItemGroup(placement: .keyboard) {
                if field == .suit {
                    Button("♣️", action: {})
                    Button("♥️", action: {})
                    Button("♠️", action: {})
                    Button("♦️", action: {})
                }
                DoneButton()
            }
        }
    }
}
```

## 获取明确的位置

- **topBarLeading**：将项目置于顶栏的前缘。
- **topBarTrailing**：将项目置于顶栏的后缘。
- **bottomBar**：将项目置于底部工具栏中。
- **bottomOrnament**：将项目置于窗口下方的装饰物中。
- **accessoryBar(id:)**：创建独特的配件栏位置。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/keyboard
crawled: 2025-12-03T06:03:12Z
---

# keyboard

**Type Property**

The item is placed in the keyboard section.

## Declaration

```swift
static let keyboard: ToolbarItemPlacement
```

## Discussion

On iOS, keyboard items are above the software keyboard when present, or at the bottom of the screen when a hardware keyboard is attached.

On macOS, keyboard items will be placed inside the Touch Bar.

A `FocusedValue`can be used to adjust the content of the keyboard bar based on the currently focused view. In the example below, the keyboard bar gains additional buttons only when the appropriate `TextField` is focused.

```swift
enum Field {
    case suit
    case rank
}

struct KeyboardBarDemo : View {
    @FocusedValue(\.field) var field: Field?

    var body: some View {
        HStack {
            TextField("Suit", text: $suitText)
                .focusedValue(\.field, .suit)
            TextField("Rank", text: $rankText)
                .focusedValue(\.field, .rank)
        }
        .toolbar {
            ToolbarItemGroup(placement: .keyboard) {
                if field == .suit {
                    Button("♣️", action: {})
                    Button("♥️", action: {})
                    Button("♠️", action: {})
                    Button("♦️", action: {})
                }
                DoneButton()
            }
        }
    }
}
```

## Getting explicit placement

- **topBarLeading**: Places the item in the leading edge of the top bar.
- **topBarTrailing**: Places the item in the trailing edge of the top bar.
- **bottomBar**: Places the item in the bottom toolbar.
- **bottomOrnament**: Places the item in an ornament under the window.
- **accessoryBar(id:)**: Creates a unique accessory bar placement.

