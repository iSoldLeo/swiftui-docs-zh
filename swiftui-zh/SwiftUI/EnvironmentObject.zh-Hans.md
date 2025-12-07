--- 来源：https://developer.apple.com/documentation/SwiftUI/EnvironmentObject
抓取时间：2025-12-02T17:32:16Z

---

# EnvironmentObject

**Structure**

父视图或祖先视图提供的可观察对象的属性包装类型。

## 声明

```swift
@MainActor @frozen @propertyWrapper @preconcurrency struct EnvironmentObject<ObjectType> where ObjectType : ObservableObject
```

## 概述

当符合 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 的可观察对象发生更改时，环境对象会使当前视图失效。如果将属性声明为环境对象，请务必通过调用其 [environmentObject(_:)](View/environmentObject.zh-Hans.md) 修饰符在祖先视图上设置相应的模型对象。

## 创建环境对象

- **init()**：创建环境对象。

## 获取值

- **wrappedValue**：环境对象引用的底层值。

- **projectedValue**：环境对象的投影，它使用动态成员查找创建与其属性的绑定。

- **EnvironmentObject.Wrapper**：底层环境对象的包装器，它可以使用动态成员查找创建与其属性的绑定。

## 在应用程序中分发模型数据

- **environmentObject(_:)**：向视图层次结构提供可观察对象。

- **environmentObject(_:)**：向视图子层次结构提供 `ObservableObject`。

## 符合以下协议：

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentObject
crawled: 2025-12-02T17:32:16Z
---

# EnvironmentObject

**Structure**

A property wrapper type for an observable object that a parent or ancestor view supplies.

## Declaration

```swift
@MainActor @frozen @propertyWrapper @preconcurrency struct EnvironmentObject<ObjectType> where ObjectType : ObservableObject
```

## Overview

An environment object invalidates the current view whenever the observable object that conforms to [doc://com.apple.documentation/documentation/Combine/ObservableObject] changes. If you declare a property as an environment object, be sure to set a corresponding model object on an ancestor view by calling its [environmentObject(_:)](View/environmentObject.zh-Hans.md) modifier.



## Creating an environment object

- **init()**: Creates an environment object.

## Getting the value

- **wrappedValue**: The underlying value referenced by the environment object.
- **projectedValue**: A projection of the environment object that creates bindings to its properties using dynamic member lookup.
- **EnvironmentObject.Wrapper**: A wrapper of the underlying environment object that can create bindings to its properties using dynamic member lookup.

## Distributing model data throughout your app

- **environmentObject(_:)**: Supplies an observable object to a view’s hierarchy.
- **environmentObject(_:)**: Supplies an `ObservableObject` to a view subhierarchy.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

