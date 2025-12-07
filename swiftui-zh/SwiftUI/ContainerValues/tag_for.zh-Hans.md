---
来源：https://developer.apple.com/documentation/SwiftUI/ContainerValues/tag(for:)
抓取时间： 2025-12-03T06:41:47Z
---

# tag(for:)

**实例方法**

如果容器值包含给定类型的标签值，则使用该标签值。

## 声明

```swift
func tag<V>(for type: V.Type) -> V? where V : Hashable
```

## 参数

- **type**：要获取标签值的类型。

## 返回值

如果子视图中有标签，则返回给定类型的标签值，否则返回 `nil`。

## 讨论

标签值是使用`View/tag`修饰符设置的。


---
source: https://developer.apple.com/documentation/SwiftUI/ContainerValues/tag(for:)
crawled: 2025-12-03T06:41:47Z
---

# tag(for:)

**Instance Method**

The tag value for the given type if the container values contains one.

## Declaration

```swift
func tag<V>(for type: V.Type) -> V? where V : Hashable
```

## Parameters

- **type**: The type to get the tag value for.

## Return Value

The tag value for the given type if the subview has one, otherwise `nil`.

## Discussion

Tag values are set using the `View/tag` modifier.

