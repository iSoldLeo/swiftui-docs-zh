---
来源： https://developer.apple.com/documentation/SwiftUI/Layout/updateCache(_:subviews:)
抓取时间： 2025-11-30T21:37:54Z
---

# updateCache(_:subviews:)

**实例方法**

当内容发生变化时更新布局的缓存。

## 声明

```swift
func updateCache(_ cache: inout Self.Cache, subviews: Self.Subviews)
```

## 参数

- **cache**：自定义布局容器方法之间共享的计算数据存储空间。
- **subviews**：代理实例集合，代表由容器排列的视图。在计算要存储到缓存中的值时，您可以使用集合中的代理来获取有关子视图的信息。

## 讨论

如果自定义布局容器通过实现 [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) 方法创建了缓存，那么当布局或其子视图发生变化时，SwiftUI 就会调用 update 方法，从而为您提供修改或使缓存内容无效的机会。该方法的默认实现是通过调用 [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) 方法来重新创建缓存，但您也可以根据需要提供自己的实现，采用增量方法。

## 管理缓存

- **makeCache(subviews:)**：为布局实例创建并初始化缓存。
- **Cache**：与布局实例相关联的缓存值。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/updateCache(_:subviews:)
crawled: 2025-11-30T21:37:54Z
---

# updateCache(_:subviews:)

**Instance Method**

Updates the layout’s cache when something changes.

## Declaration

```swift
func updateCache(_ cache: inout Self.Cache, subviews: Self.Subviews)
```

## Parameters

- **cache**: Storage for calculated data that you share among the methods of your custom layout container.
- **subviews**: A collection of proxy instances that represent the views arranged by the container. You can use the proxies in the collection to get information about the subviews as you calculate values to store in the cache.

## Discussion

If your custom layout container creates a cache by implementing the [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) method, SwiftUI calls the update method when your layout or its subviews change, giving you an opportunity to modify or invalidate the contents of the cache. The method’s default implementation recreates the cache by calling the [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) method, but you can provide your own implementation to take an incremental approach, if appropriate.

## Managing a cache

- **makeCache(subviews:)**: Creates and initializes a cache for a layout instance.
- **Cache**: Cached values associated with the layout instance.

