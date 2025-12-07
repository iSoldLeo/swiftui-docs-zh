--- 来源：https://developer.apple.com/documentation/swiftui/anyview

抓取时间：2025-12-03T07:12:47Z

---

# AnyView

**Structure**

类型擦除视图。

## 声明

```swift
@frozen struct AnyView
```

## 概述

`AnyView` 允许更改给定视图层次结构中使用的视图类型。每当使用 `AnyView` 的视图类型发生更改时，旧的层次结构将被销毁，并为新类型创建一个新的层次结构。

## 创建视图

- **init(_:)**：创建一个类型擦除 `view` 的实例。

- **init(erasing:)**

## 支持的视图类型

- **EmptyView**：不包含任何内容的视图。

- **EquatableView**：将自身与其先前值进行比较，如果新值与旧值相同，则阻止其子视图更新的视图类型。

- **SubscriptionView**：订阅带有操作的发布者的视图。

- **TupleView**：由视图值的 Swift 元组创建的视图。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/swiftui/anyview
crawled: 2025-12-03T07:12:47Z
---

# AnyView

**Structure**

A type-erased view.

## Declaration

```swift
@frozen struct AnyView
```

## Overview

An `AnyView` allows changing the type of view used in a given view hierarchy. Whenever the type of view used with an `AnyView` changes, the old hierarchy is destroyed and a new hierarchy is created for the new type.

## Creating a view

- **init(_:)**: Create an instance that type-erases `view`.
- **init(erasing:)**

## Supporting view types

- **EmptyView**: A view that doesn’t contain any content.
- **EquatableView**: A view type that compares itself against its previous value and prevents its child updating if its new value is the same as its old value.
- **SubscriptionView**: A view that subscribes to a publisher with an action.
- **TupleView**: A View created from a swift tuple of View values.

## Conforms To

- View

