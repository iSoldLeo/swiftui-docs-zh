---
来源： https://developer.apple.com/documentation/SwiftUI/FocusInteractions
抓取时间：2025-12-02T17:43:00Z
---

# FocusInteractions

**Structure**

值描述了视图可以支持的不同焦点交互。

### 声明

```swift
struct FocusInteractions
```

## 创建交互类型

- **automatic**：视图支持当前平台上交互式内容通常期望的任何焦点驱动交互。
- **activate**：视图具有可通过聚焦手势激活的主要操作。
- **edit**：视图可捕捉键盘或数字皇冠等非空间来源的输入。

## 表示视图可以接收焦点

- **focusable(_:)**：指定视图是否可聚焦。
- **focusable(_:interactions:)**：指定视图是否可聚焦，如果是，它支持哪些聚焦驱动的交互。

## 符合

- 等价
- 可表达数组字素
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/FocusInteractions
crawled: 2025-12-02T17:43:00Z
---

# FocusInteractions

**Structure**

Values describe different focus interactions that a view can support.

## Declaration

```swift
struct FocusInteractions
```

## Creating the interaction types

- **automatic**: The view supports whatever focus-driven interactions are commonly expected for interactive content on the current platform.
- **activate**: The view has a primary action that can be activated via focus gestures.
- **edit**: The view captures input from non-spatial sources like a keyboard or Digital Crown.

## Indicating that a view can receive focus

- **focusable(_:)**: Specifies if the view is focusable.
- **focusable(_:interactions:)**: Specifies if the view is focusable, and if so, what focus-driven interactions it supports.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

