--- 来源：https://developer.apple.com/documentation/SwiftUI/PlainButtonStyle/makeBody(configuration:)

抓取时间：2025-12-04T13:11:03Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示按钮主体的视图。

## 声明

```swift
@MainActor @preconcurrency func makeBody(configuration: PlainButtonStyle.Configuration) -> some View

```

## 说明

系统会针对视图层次结构中每个 [Button](../Button.zh-Hans.md) 实例调用此方法，其中该实例的当前按钮样式为该样式。


---
source: https://developer.apple.com/documentation/SwiftUI/PlainButtonStyle/makeBody(configuration:)
crawled: 2025-12-04T13:11:03Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a button.

## Declaration

```swift
@MainActor @preconcurrency func makeBody(configuration: PlainButtonStyle.Configuration) -> some View

```

## Discussion

The system calls this method for each [Button](../Button.zh-Hans.md) instance in a view hierarchy where this style is the current button style.

