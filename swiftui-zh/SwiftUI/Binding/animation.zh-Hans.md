---
来源： https://developer.apple.com/documentation/SwiftUI/Binding/animation(_:)
抓取时间： 2025-12-03T06:06:43Z
---

# animation(_:)

**实例方法**

指定绑定值发生变化时要执行的动画。

## 声明

```swift
func animation(_ animation: Animation? = .default) -> Binding<Value>
```

## 参数

- **animation**：绑定值发生变化时执行的动画序列。

## 返回值

新的绑定。

## 管理更改

- **id**：与此实例相关联的实体的稳定标识，对应于绑定的包装值的`id`。
- **transaction(_:)**：指定绑定的事务。
- **transaction**：绑定的事务。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/animation(_:)
crawled: 2025-12-03T06:06:43Z
---

# animation(_:)

**Instance Method**

Specifies an animation to perform when the binding value changes.

## Declaration

```swift
func animation(_ animation: Animation? = .default) -> Binding<Value>
```

## Parameters

- **animation**: An animation sequence performed when the binding value changes.

## Return Value

A new binding.

## Managing changes

- **id**: The stable identity of the entity associated with this instance, corresponding to the `id` of the binding’s wrapped value.
- **transaction(_:)**: Specifies a transaction for the binding.
- **transaction**: The binding’s transaction.

