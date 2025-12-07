--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusedObject
抓取时间：2025-12-02T17:43:13Z

---

# FocusedObject

**Structure**

用于包装由焦点视图或其祖先视图提供的可观察对象的属性类型。

## 声明

```swift
@MainActor @frozen @propertyWrapper @preconcurrency struct FocusedObject<ObjectType> where ObjectType : ObservableObject
```

## 概述

焦点对象会在可观察对象发生更改时使当前视图失效。如果多个视图使用相同的键发布焦点对象，则包装属性将反映距离焦点视图最近的对象。

## 创建焦点对象

- **init()**：创建一个焦点对象。

## 获取值

- **projectedValue**：聚焦对象的投影，使用动态成员查找创建与其属性的绑定。

- **wrappedValue**：聚焦对象引用的底层值。

- **FocusedObject.Wrapper**：底层聚焦对象的包装器，可以使用动态成员查找创建与其属性的绑定。

## 向聚焦视图公开引用类型

- **focusedObject(_:)**：创建一个新视图，将提供的对象公开给其他视图，这些视图的状态依赖于聚焦视图层次结构。

- **focusedSceneObject(_:)**：创建一个新视图，将提供的对象公开给其他视图，这些视图的状态依赖于活动场景。

## 符合以下规范

- DynamicProperty


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedObject
crawled: 2025-12-02T17:43:13Z
---

# FocusedObject

**Structure**

A property wrapper type for an observable object supplied by the focused view or one of its ancestors.

## Declaration

```swift
@MainActor @frozen @propertyWrapper @preconcurrency struct FocusedObject<ObjectType> where ObjectType : ObservableObject
```

## Overview

Focused objects invalidate the current view whenever the observable object changes. If multiple views publish a focused object using the same key, the wrapped property will reflect the object that’s closest to the focused view.

## Creating the focused object

- **init()**: Creates a focused object.

## Getting the value

- **projectedValue**: A projection of the focused object that creates bindings to its properties using dynamic member lookup.
- **wrappedValue**: The underlying value referenced by the focused object.
- **FocusedObject.Wrapper**: A wrapper around the underlying focused object that can create bindings to its properties using dynamic member lookup.

## Exposing reference types to focused views

- **focusedObject(_:)**: Creates a new view that exposes the provided object to other views whose whose state depends on the focused view hierarchy.
- **focusedSceneObject(_:)**: Creates a new view that exposes the provided object to other views whose whose state depends on the active scene.

## Conforms To

- DynamicProperty

