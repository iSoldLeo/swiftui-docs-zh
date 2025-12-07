--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusScope(_:)

抓取时间：2025-12-02T17:43:14Z

---

# focusScope(_:)

**实例方法**

创建一个焦点作用域，SwiftUI 使用该作用域来限制默认焦点偏好设置。

## 声明

```swift
nonisolated func focusScope(_ namespace: Namespace.ID) -> some View

```

## 参数

- **namespace**：SwiftUI 可用于限定默认焦点偏好设置的命名空间标识符。

## 返回值

一个视图，用于设置默认焦点的子视图的命名空间。

## 说明

返回的视图与提供的命名空间关联。将此命名空间传递给 [prefersDefaultFocus(_:in:)](prefersDefaultFocus___in.zh-Hans.md) 和 [resetFocus](../EnvironmentValues/resetFocus.zh-Hans.md) 函数。

## 设置聚焦范围

- **focusSection()**：表示应使用视图的框架和可聚焦子视图组来引导聚焦移动。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusScope(_:)
crawled: 2025-12-02T17:43:14Z
---

# focusScope(_:)

**Instance Method**

Creates a focus scope that SwiftUI uses to limit default focus preferences.

## Declaration

```swift
nonisolated func focusScope(_ namespace: Namespace.ID) -> some View

```

## Parameters

- **namespace**: A namespace identifier that SwiftUI can use to scope default focus preferences.

## Return Value

A view that sets the namespace of descendants for default focus.

## Discussion

The returned view gets associated with the provided namespace. Pass this namespace to [prefersDefaultFocus(_:in:)](prefersDefaultFocus___in.zh-Hans.md) and the [resetFocus](../EnvironmentValues/resetFocus.zh-Hans.md) function.

## Setting focus scope

- **focusSection()**: Indicates that the view’s frame and cohort of focusable descendants should be used to guide focus movement.

