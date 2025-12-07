---
来源： https://developer.apple.com/documentation/swiftui/tupleview
抓取时间： 2025-12-03T07:13:03Z
---

# TupleView

**Structure**

从 View 值的 swift tuple 创建的 View。

## 声明

```swift
@frozen struct TupleView<T>
```

## 创建元组视图

- **init(_:)**
- **value**

## 支持视图类型

- **AnyView**：基于类型的视图。
- **EmptyView**：不包含任何内容的视图。
- **EquatableView**：不包含任何内容的视图：一种视图类型，它将自己的值与以前的值进行比较，如果新值与旧值相同，就会阻止其子视图更新。
- **SubscriptionView**：通过操作订阅发布者的视图。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/swiftui/tupleview
crawled: 2025-12-03T07:13:03Z
---

# TupleView

**Structure**

A View created from a swift tuple of View values.

## Declaration

```swift
@frozen struct TupleView<T>
```

## Creating a tuple view

- **init(_:)**
- **value**

## Supporting view types

- **AnyView**: A type-erased view.
- **EmptyView**: A view that doesn’t contain any content.
- **EquatableView**: A view type that compares itself against its previous value and prevents its child updating if its new value is the same as its old value.
- **SubscriptionView**: A view that subscribes to a publisher with an action.

## Conforms To

- View

