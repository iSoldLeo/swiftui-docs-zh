--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressViewStyle/makeBody(configuration:)

抓取时间：2025-12-01T10:59:19Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示进度视图主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：要创建的进度视图的属性。

## 说明

视图层级结构会为每个当前使用此样式的进度视图调用此方法。

## 创建自定义进度视图样式

- **ProgressViewStyle.Configuration**：进度视图实例属性的类型别名。

- **Body**：表示进度视图主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressViewStyle/makeBody(configuration:)
crawled: 2025-12-01T10:59:19Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view representing the body of a progress view.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the progress view being created.

## Discussion

The view hierarchy calls this method for each progress view where this style is the current progress view style.

## Creating custom progress view styles

- **ProgressViewStyle.Configuration**: A type alias for the properties of a progress view instance.
- **Body**: A view representing the body of a progress view.

