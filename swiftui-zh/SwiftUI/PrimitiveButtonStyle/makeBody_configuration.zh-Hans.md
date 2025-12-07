---
来源：https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/makeBody(配置:)
抓取时间：2025-12-01T10:58:01Z
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

## 创建自定义按钮样式

- **PrimitiveButtonStyle.Configuration**：按钮的属性。
- **Body**：表示按钮主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/makeBody(configuration:)
crawled: 2025-12-01T10:58:01Z
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

## Creating custom button styles

- **PrimitiveButtonStyle.Configuration**: The properties of a button.
- **Body**: A view that represents the body of a button.

