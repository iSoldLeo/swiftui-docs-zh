---
来源： https://developer.apple.com/documentation/SwiftUI/ColorScheme
抓取时间： 2025-12-02T17:32:45Z
---

# ColorScheme

**Enumeration**

可能的配色方案，分别对应浅色和深色外观。

## 声明

```swift
enum ColorScheme
```

## 概览

读取[colorScheme](EnvironmentValues/colorScheme.zh-Hans.md) 环境值时，您会收到一个配色方案值。该值会告诉您当前视图适用的是浅色还是深色外观。只要外观发生变化，SwiftUI 就会更新该值，并重新绘制依赖于该值的视图。例如，下面的[Text](Text.zh-Hans.md) 视图会在用户启用 "黑暗模式 "时自动更新：

```swift
@Environment(\.colorScheme) private var colorScheme

var body: some View {
    Text(colorScheme == .dark ? "Dark" : "Light")
}
```

使用[preferredColorScheme(_:)](View/preferredColorScheme.zh-Hans.md) 视图修饰符为特定视图层次结构设置首选外观，以覆盖用户的 "黑暗模式 "设置。

## 获取配色方案

- **ColorScheme.light**：与浅色外观相对应的配色方案。
- **ColorScheme.dark**：与深色外观相对应的配色方案。

## 创建配色方案

- **init(_:)**：从等同的用户界面样式创建配色方案。

## 支持类型

- **PreferredColorSchemeKey**：用于指定首选配色方案的键。

## 检测和请求明暗外观

- **preferredColorScheme(_:)**：设置此演示文稿的首选色彩方案。
- **colorScheme**：此环境的配色方案。

## 符合

- CaseIterable
- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ColorScheme
crawled: 2025-12-02T17:32:45Z
---

# ColorScheme

**Enumeration**

The possible color schemes, corresponding to the light and dark appearances.

## Declaration

```swift
enum ColorScheme
```

## Overview

You receive a color scheme value when you read the [colorScheme](EnvironmentValues/colorScheme.zh-Hans.md) environment value. The value tells you if a light or dark appearance currently applies to the view. SwiftUI updates the value whenever the appearance changes, and redraws views that depend on the value. For example, the following [Text](Text.zh-Hans.md) view automatically updates when the user enables Dark Mode:

```swift
@Environment(\.colorScheme) private var colorScheme

var body: some View {
    Text(colorScheme == .dark ? "Dark" : "Light")
}
```

Set a preferred appearance for a particular view hierarchy to override the user’s Dark Mode setting using the [preferredColorScheme(_:)](View/preferredColorScheme.zh-Hans.md) view modifier.

## Getting color schemes

- **ColorScheme.light**: The color scheme that corresponds to a light appearance.
- **ColorScheme.dark**: The color scheme that corresponds to a dark appearance.

## Creating a color scheme

- **init(_:)**: Creates a color scheme from its user interface style equivalent.

## Supporting types

- **PreferredColorSchemeKey**: A key for specifying the preferred color scheme.

## Detecting and requesting the light or dark appearance

- **preferredColorScheme(_:)**: Sets the preferred color scheme for this presentation.
- **colorScheme**: The color scheme of this environment.

## Conforms To

- CaseIterable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

