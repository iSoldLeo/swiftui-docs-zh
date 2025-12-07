--- 来源：https://developer.apple.com/documentation/SwiftUI/Subview

抓取时间：2025-12-02T17:27:55Z

---

# 子视图

**Structure**

一个不透明值，表示另一个视图的子视图。

## 声明

```swift
struct Subview
```

## 概述

可以通过使用 `ForEach(subviews:)` 或 `Group(subviews:)` 来访问 `Subview`。

子视图是其所代表的已解析视图的代理，这意味着应用于原始视图的修饰符会优先于应用于子视图的修饰符生效，并且视图是使用其容器的环境来解析的，而不是使用其子视图代理的环境。此外，由于子视图必须代表单个叶视图或容器，因此子视图可能代表应用样式后的视图。因此，尝试对其应用样式可能无效。

## 结构

- **Subview.ID**：子视图的唯一标识符。

## 实例属性

- **containerValues**：与给定子视图关联的容器值。

- **id**：视图的唯一标识符。

## 枚举

- **Subview.ContainerSizingOptions**：容器中所有子视图的大小设置选项。

## 访问容器的子视图

- **SubviewsCollection**：表示视图子视图的不透明集合。

- **SubviewsCollectionSlice**：子视图集合的一个切片。

- **containerValue(_:_:)**：设置视图的特定容器值。

- **ContainerValues**：与给定视图关联的容器值集合。

- **ContainerValueKey**：用于访问容器值的键。

## 符合以下规范

- 可识别的

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/Subview
crawled: 2025-12-02T17:27:55Z
---

# Subview

**Structure**

An opaque value representing a subview of another view.

## Declaration

```swift
struct Subview
```

## Overview

Access to a `Subview` can be obtained by using `ForEach(subviews:)` or `Group(subviews:)`.

Subviews are proxies to the resolved view they represent, meaning that modifiers applied to the original view will be applied before modifiers applied to the subview, and the view is resolved using the environment of its container, *not* the environment of the its subview proxy. Additionally, because subviews must represent a single leaf view, or container, a subview may represent a view after the application of styles. As such, attempting to apply a style to it may have no affect.

## Structures

- **Subview.ID**: A unique identifier for a subview.

## Instance Properties

- **containerValues**: The container values associated with the given subview.
- **id**: The unique identifier of the view.

## Enumerations

- **Subview.ContainerSizingOptions**: Options on how all subviews should be sized when in a container.

## Accessing a container’s subviews

- **SubviewsCollection**: An opaque collection representing the subviews of view.
- **SubviewsCollectionSlice**: A slice of a SubviewsCollection.
- **containerValue(_:_:)**: Sets a particular container value of a view.
- **ContainerValues**: A collection of container values associated with a given view.
- **ContainerValueKey**: A key for accessing container values.

## Conforms To

- Identifiable
- View

