---
来源： https://developer.apple.com/documentation/SwiftUI/RedactionReasons
抓取时间：2025-12-02T17:32:57Z
---

# RedactionReasons

**Structure**

对屏幕上显示的数据进行编辑的原因。

## 声明

```swift
struct RedactionReasons
```

## 获取编辑原因

- **invalidated**：显示的数据应显示为已失效并等待新的更新。
- **placeholder**：显示的数据应显示为通用占位符。
- **privacy**：显示的数据应模糊不清，以保护私人信息。

## 创建编辑理由

- **init(rawValue:)**：从原始值创建一个新集合。
- **rawValue**：原始值。

## 隐藏私人内容

- 为始终保持开启状态设计应用程序**：定制 watchOS 应用程序的用户界面，以实现连续显示。
- **privacySensitive(_:)**：将视图标记为包含敏感的私人用户数据。
- **redacted(reason:)**：添加对该视图层次结构应用编辑的理由。
- **unredacted()**：删除对该视图层次结构应用节录的任何理由。
- **redactionReasons**：当前应用于视图层次结构的编辑理由。
- **isSceneCaptured**：当前的捕获状态。

## 符合

- 等价
- 可通过数组原语表达
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/RedactionReasons
crawled: 2025-12-02T17:32:57Z
---

# RedactionReasons

**Structure**

The reasons to apply a redaction to data displayed on screen.

## Declaration

```swift
struct RedactionReasons
```

## Getting redaction reasons

- **invalidated**: Displayed data should appear as invalidated and pending a new update.
- **placeholder**: Displayed data should appear as generic placeholders.
- **privacy**: Displayed data should be obscured to protect private information.

## Creating redaction reasons

- **init(rawValue:)**: Creates a new set from a raw value.
- **rawValue**: The raw value.

## Redacting private content

- **Designing your app for the Always On state**: Customize your watchOS app’s user interface for continuous display.
- **privacySensitive(_:)**: Marks the view as containing sensitive, private user data.
- **redacted(reason:)**: Adds a reason to apply a redaction to this view hierarchy.
- **unredacted()**: Removes any reason to apply a redaction to this view hierarchy.
- **redactionReasons**: The current redaction reasons applied to the view hierarchy.
- **isSceneCaptured**: The current capture state.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

