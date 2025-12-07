--- 来源：https://developer.apple.com/documentation/SwiftUI/View/environmentObject(_:)

抓取时间：2025-12-02T17:32:15Z

---

# environmentObject(_:)

**实例方法**

向视图的层级结构提供一个可观察对象。

## 声明

```swift
nonisolated func environmentObject<T>(_ object: T) -> some View where T : ObservableObject

```

## 参数

- **object**：要存储并使其可供视图层级结构使用的对象。

## 说明

使用此修饰符将可观察对象添加到视图的环境中。该对象必须符合 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 协议。

将对象添加到视图的环境中，即可使该对象可供视图层级结构中的子视图使用。要在子视图中检索对象，请使用 [EnvironmentObject](../EnvironmentObject.zh-Hans.md) 属性包装器。

## 在应用程序中分发模型数据

- **environmentObject(_:)**：为视图子层次结构提供 `ObservableObject`。

- **EnvironmentObject**：父视图或祖先视图提供的可观察对象的属性包装器类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/environmentObject(_:)
crawled: 2025-12-02T17:32:15Z
---

# environmentObject(_:)

**Instance Method**

Supplies an observable object to a view’s hierarchy.

## Declaration

```swift
nonisolated func environmentObject<T>(_ object: T) -> some View where T : ObservableObject

```

## Parameters

- **object**: The object to store and make available to the view’s hierarchy.

## Discussion

Use this modifier to add an observable object to a view’s environment. The object must conform to the [doc://com.apple.documentation/documentation/Combine/ObservableObject] protocol.

Adding an object to a view’s environment makes the object available to subviews in the view’s hierarchy. To retrieve the object in a subview, use the [EnvironmentObject](../EnvironmentObject.zh-Hans.md) property wrapper.



## Distributing model data throughout your app

- **environmentObject(_:)**: Supplies an `ObservableObject` to a view subhierarchy.
- **EnvironmentObject**: A property wrapper type for an observable object that a parent or ancestor view supplies.

