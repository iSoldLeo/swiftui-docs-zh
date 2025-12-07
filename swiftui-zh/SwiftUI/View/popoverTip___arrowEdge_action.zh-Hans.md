--- 来源：https://developer.apple.com/documentation/SwiftUI/View/popoverTip(_:arrowEdge:action:)

抓取时间：2025-11-30T21:10:11Z

---

# popoverTip(_:arrowEdge:action:)

**实例方法**

在修改后的视图上显示弹出提示。

## 声明

```swift
@preconcurrency nonisolated func popoverTip(_ tip: (any Tip)?, arrowEdge: Edge? = nil, action: @escaping @MainActor (Tips.Action) -> Void = { _ in }) -> some View

```

## 参数

- **tip**：要显示的提示。

- **arrowEdge**：定义弹出提示箭头位置的 attachmentAnchor 的边缘。默认情况下，系统会选择弹出提示箭头的最佳方向。

- **action**：用户点击提示按钮时要执行的操作。

### 讨论

当提示信息符合显示条件时，使用此修饰符可在现有视图中以弹出框的形式显示提示信息。

```swift
import SwiftUI
import TipKit

// Define your tip's content.
struct SampleTip: Tip {
    var title: Text {
        Text("Save as a Favorite")
    }

    var message: Text? {
        Text("Your favorite backyards always appear at the top of the list.")
    }

    var image: Image? {
        Image(systemName: "star")
    }
}

struct SampleView: View {
    // Create an instance of your tip.
    var tip = SampleTip()

    var body: some View {
        VStack {
            // Add `.popoverTip` to the view you want to modify.
            // Tips.configure(options:) must be called before your tip will be eligible for display.
            Image(systemName: "star")
                .popoverTip(tip)
        }
    }
}
```

## 提供提示信息

- **tipBackground(_:)**：设置提示信息视图的背景样式。目前仅适用于内嵌提示信息，不适用于弹出框提示信息。

- **tipCornerRadius(_:antialiased:)**：设置内嵌提示信息视图的圆角半径。

- **tipImageSize(_:)**：设置提示信息图像的大小。

- **tipViewStyle(_:)**：设置视图层级结构中 TipView 的样式。

- **tipImageStyle(_:)**：设置提示信息图像的样式。

- **tipImageStyle(_:_:)**：设置提示信息图像的样式。

- **tipImageStyle(_:_:_:)**：设置提示图片的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/popoverTip(_:arrowEdge:action:)
crawled: 2025-11-30T21:10:11Z
---

# popoverTip(_:arrowEdge:action:)

**Instance Method**

Presents a popover tip on the modified view.

## Declaration

```swift
@preconcurrency nonisolated func popoverTip(_ tip: (any Tip)?, arrowEdge: Edge? = nil, action: @escaping @MainActor (Tips.Action) -> Void = { _ in }) -> some View

```

## Parameters

- **tip**: The tip to display.
- **arrowEdge**: The edge of the attachmentAnchor that defines the location of the popover’s arrow. By default, the system will choose the best orientation of the popover’s arrow.
- **action**: The action to perform when the user triggers a tip’s button.

### Discussion

Use this modifier to present a tip as a popover on an existing view when the tip becomes eligible for display.

```swift
import SwiftUI
import TipKit

// Define your tip's content.
struct SampleTip: Tip {
    var title: Text {
        Text("Save as a Favorite")
    }

    var message: Text? {
        Text("Your favorite backyards always appear at the top of the list.")
    }

    var image: Image? {
        Image(systemName: "star")
    }
}

struct SampleView: View {
    // Create an instance of your tip.
    var tip = SampleTip()

    var body: some View {
        VStack {
            // Add `.popoverTip` to the view you want to modify.
            // Tips.configure(options:) must be called before your tip will be eligible for display.
            Image(systemName: "star")
                .popoverTip(tip)
        }
    }
}
```

## Providing tips

- **tipBackground(_:)**: Sets the tip’s view background to a style. Currently this only applies to inline tips, not popover tips.
- **tipCornerRadius(_:antialiased:)**: Sets the corner radius for an inline tip view.
- **tipImageSize(_:)**: Sets the size for a tip’s image.
- **tipViewStyle(_:)**: Sets the given style for TipView within the view hierarchy.
- **tipImageStyle(_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:_:)**: Sets the style for a tip’s image.

