--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationDetent
抓取时间：2025-12-02T17:30:17Z

---

# PresentationDetent

**Structure**

表示工作表自然放置高度的类型。

## 声明

```swift
struct PresentationDetent
```

## 获取内置定位点

- **large**：工作表处于全高时的系统定位点。

- **medium**：工作表高度约为屏幕一半时的系统定位点，在紧凑高度模式下处于非活动状态。

## 创建自定义定位点

- **custom(_:)**：具有计算高度的自定义定位点。

- **fraction(_:)**：具有指定分数高度的自定义定位点。

- **height(_:)**：具有指定高度的自定义定位点。

- **PresentationDetent.Context**：用于计算演示文稿高度的信息。

## 配置工作表高度

- **presentationDetents(_:)**：设置包含工作表的可用定位点。

- **presentationDetents(_:selection:)**：设置包含工作表的可用定位点，使您可以通过编程方式控制当前选定的定位点。

- **presentationContentInteraction(_:)**：配置演示文稿中滑动操作的行为。

- **presentationDragIndicator(_:)**：设置工作表顶部拖动指示器的可见性。

- **CustomPresentationDetent**：自定义定位点的定义，具有计算高度。

- **PresentationContentInteraction**：可用于影响演示文稿对滑动操作响应方式的行为。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationDetent
crawled: 2025-12-02T17:30:17Z
---

# PresentationDetent

**Structure**

A type that represents a height where a sheet naturally rests.

## Declaration

```swift
struct PresentationDetent
```

## Getting built-in detents

- **large**: The system detent for a sheet at full height.
- **medium**: The system detent for a sheet that’s approximately half the height of the screen, and is inactive in compact height.

## Creating custom detents

- **custom(_:)**: A custom detent with a calculated height.
- **fraction(_:)**: A custom detent with the specified fractional height.
- **height(_:)**: A custom detent with the specified height.
- **PresentationDetent.Context**: Information that you use to calculate the presentation’s height.

## Configuring a sheet’s height

- **presentationDetents(_:)**: Sets the available detents for the enclosing sheet.
- **presentationDetents(_:selection:)**: Sets the available detents for the enclosing sheet, giving you programmatic control of the currently selected detent.
- **presentationContentInteraction(_:)**: Configures the behavior of swipe gestures on a presentation.
- **presentationDragIndicator(_:)**: Sets the visibility of the drag indicator on top of a sheet.
- **CustomPresentationDetent**: The definition of a custom detent with a calculated height.
- **PresentationContentInteraction**: A behavior that you can use to influence how a presentation responds to swipe gestures.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

