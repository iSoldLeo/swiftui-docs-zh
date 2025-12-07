--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessoryBarActionButtonStyle/makeBody(configuration:)

抓取时间：2025-12-04T13:10:53Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示按钮主体的视图。

## 声明

```swift
@MainActor @preconcurrency func makeBody(configuration: AccessoryBarActionButtonStyle.Configuration) -> some View

```

## 参数

- **configuration**：按钮的属性。

## 说明

系统会针对视图层次结构中每个 [Button](../Button.zh-Hans.md) 实例调用此方法，前提是该实例的当前按钮样式为该样式。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessoryBarActionButtonStyle/makeBody(configuration:)
crawled: 2025-12-04T13:10:53Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a button.

## Declaration

```swift
@MainActor @preconcurrency func makeBody(configuration: AccessoryBarActionButtonStyle.Configuration) -> some View

```

## Parameters

- **configuration**: The properties of the button.

## Discussion

The system calls this method for each [Button](../Button.zh-Hans.md) instance in a view hierarchy where this style is the current button style.

