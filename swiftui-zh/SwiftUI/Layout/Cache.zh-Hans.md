---
来源： https://developer.apple.com/documentation/SwiftUI/Layout/Cache
抓取时间： 2025-12-02T17:53:11Z
---

# 缓存

**相关类型**

与布局实例相关的缓存值。

## 声明

```swift
associatedtype Cache = Void
```

## 讨论

如果为自定义布局创建缓存，可以使用类型别名将其定义为数据存储类型。或者，也可以在使用缓存的所有地方直接引用数据存储类型。

更多信息，请参见 [makeCache(subviews:)](makeCache_subviews.zh-Hans.md)。

## 管理缓存

- **makeCache(subviews:)**：为布局实例创建并初始化缓存。
- **updateCache(_:subviews:)**：当内容发生变化时更新布局的缓存。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/Cache
crawled: 2025-12-02T17:53:11Z
---

# Cache

**Associated Type**

Cached values associated with the layout instance.

## Declaration

```swift
associatedtype Cache = Void
```

## Discussion

If you create a cache for your custom layout, you can use a type alias to define this type as your data storage type. Alternatively, you can refer to the data storage type directly in all the places where you work with the cache.

See [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) for more information.

## Managing a cache

- **makeCache(subviews:)**: Creates and initializes a cache for a layout instance.
- **updateCache(_:subviews:)**: Updates the layout’s cache when something changes.

