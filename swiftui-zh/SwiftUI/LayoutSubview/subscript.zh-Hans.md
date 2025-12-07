---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubview/subscript(_:)
抓取时间： 2025-12-01T00:43:14Z
---

# 下标(_:)

**实例下标**

获取与指定键相关联的子视图的值。

## 声明

```swift
subscript<K>(key: K.Type) -> K.Value where K : LayoutValueKey { get }
```

## 概览

如果使用[LayoutValueKey](../LayoutValueKey.zh-Hans.md) 定义了自定义布局值，则可以通过索引布局容器中与键类型相关的子视图，读取该容器中指定子视图的键相关值。例如，如果定义了一个`Flexibility`键类型，就可以将布局中所有子视图的关联值放入一个数组中：

```swift
let flexibilities = subviews.map { subview in
    subview[Flexibility.self]
}
```

有关创建自定义布局的更多信息，请参阅 [Layout](../Layout.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubview/subscript(_:)
crawled: 2025-12-01T00:43:14Z
---

# subscript(_:)

**Instance Subscript**

Gets the value for the subview that’s associated with the specified key.

## Declaration

```swift
subscript<K>(key: K.Type) -> K.Value where K : LayoutValueKey { get }
```

## Overview

If you define a custom layout value using [LayoutValueKey](../LayoutValueKey.zh-Hans.md), you can read the key’s associated value for a given subview in a layout container by indexing the container’s subviews with the key type. For example, if you define a `Flexibility` key type, you can put the associated values of all the layout’s subviews into an array:

```swift
let flexibilities = subviews.map { subview in
    subview[Flexibility.self]
}
```

For more information about creating a custom layout, see [Layout](../Layout.zh-Hans.md).

