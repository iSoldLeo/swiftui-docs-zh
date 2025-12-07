---
来源：https://developer.apple.com/documentation/SwiftUI/ButtonStyle/makeBody(配置：)
抓取时间：2025-12-01T10:57:58Z
---

# makeBody(configuration:)

**实例方法**

创建表示按钮主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 讨论

系统会为视图层次结构中的每个[Button](../Button.zh-Hans.md) 实例调用此方法，其中该样式是当前按钮样式。

## 自定义按钮样式

- **ButtonStyle.Configuration**：按钮的属性。
- **Body**：表示按钮主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonStyle/makeBody(configuration:)
crawled: 2025-12-01T10:57:58Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a button.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Discussion

The system calls this method for each [Button](../Button.zh-Hans.md) instance in a view hierarchy where this style is the current button style.

## Custom button styles

- **ButtonStyle.Configuration**: The properties of a button.
- **Body**: A view that represents the body of a button.

