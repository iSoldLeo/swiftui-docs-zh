--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomPresentationDetent
抓取时间：2025-12-02T17:30:18Z

---

# CustomPresentationDetent

**Protocol**

自定义定位点的定义，并计算其高度。

## 声明

```swift
protocol CustomPresentationDetent
```

## 概述

您可以创建和使用带有内置定位点的自定义定位点。

```swift
extension PresentationDetent {
    static let bar = Self.custom(BarDetent.self)
    static let small = Self.height(100)
    static let extraLarge = Self.fraction(0.75)
}

private struct BarDetent: CustomPresentationDetent {
    static func height(in context: Context) -> CGFloat? {
        max(44, context.maxDetentValue * 0.1)
    }
}

struct ContentView: View {
    @State private var showSettings = false
    @State private var selectedDetent = PresentationDetent.bar

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView(selectedDetent: $selectedDetent)
                .presentationDetents(
                    [.bar, .small, .medium, .large, .extraLarge],
                    selection: $selectedDetent)
        }
    }
}
```

## 获取高度

- **height(in:)**：根据上下文计算并返回高度。

- **CustomPresentationDetent.Context**：可用于计算自定义定位点高度的信息。

## 配置工作表高度

- **presentationDetents(_:)**：设置包含工作表的可用位置。

- **presentationDetents(_:selection:)**：设置包含工作表的可用位置，允许您通过编程方式控制当前选定的位置。

- **presentationContentInteraction(_:)**：配置演示文稿中滑动操作的行为。

- **presentationDragIndicator(_:)**：设置工作表顶部拖动指示器的可见性。

- **PresentationDetent**：表示工作表自然放置高度的类型。

- **PresentationContentInteraction**：可用于影响演示文稿对滑动操作响应方式的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomPresentationDetent
crawled: 2025-12-02T17:30:18Z
---

# CustomPresentationDetent

**Protocol**

The definition of a custom detent with a calculated height.

## Declaration

```swift
protocol CustomPresentationDetent
```

## Overview

You can create and use a custom detent with built-in detents.

```swift
extension PresentationDetent {
    static let bar = Self.custom(BarDetent.self)
    static let small = Self.height(100)
    static let extraLarge = Self.fraction(0.75)
}

private struct BarDetent: CustomPresentationDetent {
    static func height(in context: Context) -> CGFloat? {
        max(44, context.maxDetentValue * 0.1)
    }
}

struct ContentView: View {
    @State private var showSettings = false
    @State private var selectedDetent = PresentationDetent.bar

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView(selectedDetent: $selectedDetent)
                .presentationDetents(
                    [.bar, .small, .medium, .large, .extraLarge],
                    selection: $selectedDetent)
        }
    }
}
```

## Getting the height

- **height(in:)**: Calculates and returns a height based on the context.
- **CustomPresentationDetent.Context**: Information that you can use to calculate the height of a custom detent.

## Configuring a sheet’s height

- **presentationDetents(_:)**: Sets the available detents for the enclosing sheet.
- **presentationDetents(_:selection:)**: Sets the available detents for the enclosing sheet, giving you programmatic control of the currently selected detent.
- **presentationContentInteraction(_:)**: Configures the behavior of swipe gestures on a presentation.
- **presentationDragIndicator(_:)**: Sets the visibility of the drag indicator on top of a sheet.
- **PresentationDetent**: A type that represents a height where a sheet naturally rests.
- **PresentationContentInteraction**: A behavior that you can use to influence how a presentation responds to swipe gestures.

