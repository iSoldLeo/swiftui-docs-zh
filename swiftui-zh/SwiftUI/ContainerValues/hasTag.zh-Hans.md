---
来源： https://developer.apple.com/documentation/SwiftUI/ContainerValues/hasTag(_:)
抓取时间： 2025-12-03T06:41:46Z
---

# hasTag(_:)

**实例方法**

如果容器值包含与给定值匹配的标记，则返回 true。

## 声明

```swift
func hasTag<V>(_ tag: V) -> Bool where V : Hashable
```

## 参数

- **tag**：要检查的标记值。

## 返回值

容器值是否有与给定值匹配的标记。

## 讨论

标签值是使用`View/tag`修饰符设置的。


---
source: https://developer.apple.com/documentation/SwiftUI/ContainerValues/hasTag(_:)
crawled: 2025-12-03T06:41:46Z
---

# hasTag(_:)

**Instance Method**

Returns true if the container values contain a tag matching a given value.

## Declaration

```swift
func hasTag<V>(_ tag: V) -> Bool where V : Hashable
```

## Parameters

- **tag**: The tag value to check for.

## Return Value

If the container values has a tag matching the given value.

## Discussion

Tag values are set using the `View/tag` modifier.

