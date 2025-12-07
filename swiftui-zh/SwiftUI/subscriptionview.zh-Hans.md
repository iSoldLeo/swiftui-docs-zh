--- 来源：https://developer.apple.com/documentation/swiftui/subscriptionview

抓取时间：2025-12-03T07:13:01Z

---

# SubscriptionView

**Structure**

一个通过操作订阅发布者的视图。

## 声明

```swift
@frozen struct SubscriptionView<PublisherType, Content> where PublisherType : Publisher, Content : View, PublisherType.Failure == Never
```

## 创建订阅视图

- **init(content:publisher:action:)**

## 管理订阅

- **publisher**：被订阅的 `Publisher`。

- **action**：当 `publisher` 发出事件时执行的 `Action`。

- **content**：内容视图。

## 支持的视图类型

- **AnyView**：类型擦除视图。

- **EmptyView**：不包含任何内容的视图。

- **EquatableView**：一种视图类型，它会将自身与其先前的值进行比较，如果新值与旧值相同，则阻止其子视图更新。

- **TupleView**：由 Swift 元组（包含视图值）创建的视图。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/swiftui/subscriptionview
crawled: 2025-12-03T07:13:01Z
---

# SubscriptionView

**Structure**

A view that subscribes to a publisher with an action.

## Declaration

```swift
@frozen struct SubscriptionView<PublisherType, Content> where PublisherType : Publisher, Content : View, PublisherType.Failure == Never
```

## Creating a subscription view

- **init(content:publisher:action:)**

## Managing the subscription

- **publisher**: The `Publisher` that is being subscribed.
- **action**: The `Action` executed when `publisher` emits an event.
- **content**: The content view.

## Supporting view types

- **AnyView**: A type-erased view.
- **EmptyView**: A view that doesn’t contain any content.
- **EquatableView**: A view type that compares itself against its previous value and prevents its child updating if its new value is the same as its old value.
- **TupleView**: A View created from a swift tuple of View values.

## Conforms To

- View

