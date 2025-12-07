---
来源：https://developer.apple.com/documentation/SwiftUI/CardButtonStyle/makeBody(配置：)
抓取时间：2025-12-04T13:10:59Z
---

# makeBody(configuration:)

**实例方法**

创建表示按钮主体的视图。

## 声明

```swift
@MainActor @preconcurrency func makeBody(configuration: CardButtonStyle.Configuration) -> some View

```

## 参数

- **configuration**：按钮的属性。

## 讨论

系统会为视图层次结构中的每个[Button](../Button.zh-Hans.md) 实例调用此方法，其中[CardButtonStyle](../CardButtonStyle.zh-Hans.md) 是当前的按钮样式。


---
source: https://developer.apple.com/documentation/SwiftUI/CardButtonStyle/makeBody(configuration:)
crawled: 2025-12-04T13:10:59Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a button.

## Declaration

```swift
@MainActor @preconcurrency func makeBody(configuration: CardButtonStyle.Configuration) -> some View

```

## Parameters

- **configuration**: The properties of the button.

## Discussion

The system calls this method for each [Button](../Button.zh-Hans.md) instance in a view hierarchy in which [CardButtonStyle](../CardButtonStyle.zh-Hans.md) is the current button style.

