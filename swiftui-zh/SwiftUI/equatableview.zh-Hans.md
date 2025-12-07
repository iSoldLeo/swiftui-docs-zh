---
来源： https://developer.apple.com/documentation/swiftui/equatableview
抓取时间： 2025-12-03T07:12:49Z
---

# EquatableView

**Structure**

一种视图类型，它将自己的值与之前的值进行比较，如果新值与旧值相同，则会阻止其子视图更新。

### 声明

```swift
@frozen struct EquatableView<Content> where Content : Equatable, Content : View
```

## 创建等价视图

- **init(content:)**
- **content**

## 支持视图类型

- **AnyView**：基于类型的视图。
- **EmptyView**：不包含任何内容的视图。
- **SubscriptionView**：不包含任何内容的视图：通过操作订阅发布者的视图。
- **TupleView**：从 View 值的敏捷元组创建的 View。

## 符合

- 符合


---
source: https://developer.apple.com/documentation/swiftui/equatableview
crawled: 2025-12-03T07:12:49Z
---

# EquatableView

**Structure**

A view type that compares itself against its previous value and prevents its child updating if its new value is the same as its old value.

## Declaration

```swift
@frozen struct EquatableView<Content> where Content : Equatable, Content : View
```

## Creating an equatable view

- **init(content:)**
- **content**

## Supporting view types

- **AnyView**: A type-erased view.
- **EmptyView**: A view that doesn’t contain any content.
- **SubscriptionView**: A view that subscribes to a publisher with an action.
- **TupleView**: A View created from a swift tuple of View values.

## Conforms To

- View

