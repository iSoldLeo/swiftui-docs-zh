---
来源： https://developer.apple.com/documentation/SwiftUI/EmptyView
抓取时间： 2025-12-02T16:02:44Z
---

# 空视图

**Structure**

不包含任何内容的视图。

## 声明

```swift
@frozen struct EmptyView
```

## 概览

您很少需要直接创建`EmptyView`。相反，`EmptyView` 表示没有视图。

在 SwiftUI 视图类型定义了一个或多个带有通用参数的子视图并允许子视图缺席的情况下，SwiftUI 会使用`EmptyView`。不存在时，通用类型参数中的子视图类型为 `EmptyView`。

下面的示例创建了一个不带标签的不定[ProgressView](ProgressView.zh-Hans.md)。[ProgressView](ProgressView.zh-Hans.md)类型声明了两个通用参数`Label`和`CurrentValueLabel`，用于其子视图使用的类型。当两个子视图都不存在时（如此处），结果类型为`ProgressView<EmptyView, EmptyView>`，如示例输出所示：

```swift
let progressView = ProgressView()
print("\(type(of:progressView))")
// Prints: ProgressView<EmptyView, EmptyView>
```

## 创建一个空视图

- **init()**：创建一个空视图。

## 支持的视图类型

- **AnyView**：类型区分的视图。
- **EquatableView**：一种视图类型，它将自己的值与以前的值进行比较，如果新值与旧值相同，就会阻止其子视图更新。
- **SubscriptionView**：通过操作订阅发布者的视图。
- **TupleView**：从 View 值的敏捷元组创建的 View。

## 符合

- 比特可复制
- 可复制
- 可发送
- 可发送元类型
- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/EmptyView
crawled: 2025-12-02T16:02:44Z
---

# EmptyView

**Structure**

A view that doesn’t contain any content.

## Declaration

```swift
@frozen struct EmptyView
```

## Overview

You will rarely, if ever, need to create an `EmptyView` directly. Instead, `EmptyView` represents the absence of a view.

SwiftUI uses `EmptyView` in situations where a SwiftUI view type defines one or more child views with generic parameters, and allows the child views to be absent. When absent, the child view’s type in the generic type parameter is `EmptyView`.

The following example creates an indeterminate [ProgressView](ProgressView.zh-Hans.md) without a label. The [ProgressView](ProgressView.zh-Hans.md) type declares two generic parameters, `Label` and `CurrentValueLabel`, for the types used by its subviews. When both subviews are absent, like they are here, the resulting type is `ProgressView<EmptyView, EmptyView>`, as indicated by the example’s output:

```swift
let progressView = ProgressView()
print("\(type(of:progressView))")
// Prints: ProgressView<EmptyView, EmptyView>
```

## Creating an empty view

- **init()**: Creates an empty view.

## Supporting view types

- **AnyView**: A type-erased view.
- **EquatableView**: A view type that compares itself against its previous value and prevents its child updating if its new value is the same as its old value.
- **SubscriptionView**: A view that subscribes to a publisher with an action.
- **TupleView**: A View created from a swift tuple of View values.

## Conforms To

- BitwiseCopyable
- Copyable
- Sendable
- SendableMetatype
- View

