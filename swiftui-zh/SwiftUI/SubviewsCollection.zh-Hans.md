--- 来源：https://developer.apple.com/documentation/SwiftUI/SubviewsCollection

抓取时间：2025-12-02T17:27:55Z

---

# SubviewsCollection

**Structure**

一个表示视图子视图的不透明集合。

## 声明

```swift
struct SubviewsCollection
```

## 概述

Subviews 集合按需构建子视图，因此只需访问创建最终内容所需的集合部分即可。

您可以使用 `Group/init(sectionsOf:transform:)` 初始化器访问视图的子视图集合。

集合的元素是构成给定视图的各个部分，整个集合充当原始视图的代理。

## 访问容器的子视图

- **Subview**：表示另一个视图的子视图的不透明值。

- **SubviewsCollectionSlice**：SubviewsCollection 的一个切片。

- **containerValue(_:_:)**：设置视图的特定容器值。

- **ContainerValues**：与给定视图关联的容器值的集合。

- **ContainerValueKey**：用于访问容器值的键。

## 符合以下协议：

- BidirectionalCollection

- Collection

- Copyable

- RandomAccessCollection

- Sequence

- View


---
source: https://developer.apple.com/documentation/SwiftUI/SubviewsCollection
crawled: 2025-12-02T17:27:55Z
---

# SubviewsCollection

**Structure**

An opaque collection representing the subviews of view.

## Declaration

```swift
struct SubviewsCollection
```

## Overview

Subviews collection constructs subviews on demand, so only access the part of the collection you need to create the resulting content.

You can get access to a view’s subview collection by using the `Group/init(sectionsOf:transform:)` initializer.

The collection’s elements are the pieces that make up the given view, and the collection as a whole acts as a proxy for the original view.

## Accessing a container’s subviews

- **Subview**: An opaque value representing a subview of another view.
- **SubviewsCollectionSlice**: A slice of a SubviewsCollection.
- **containerValue(_:_:)**: Sets a particular container value of a view.
- **ContainerValues**: A collection of container values associated with a given view.
- **ContainerValueKey**: A key for accessing container values.

## Conforms To

- BidirectionalCollection
- Collection
- Copyable
- RandomAccessCollection
- Sequence
- View

