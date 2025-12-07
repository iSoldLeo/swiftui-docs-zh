---
来源： https://developer.apple.com/documentation/SwiftUI/Layout/makeCache(子视图：)
抓取时间： 2025-12-02T17:53:10Z
---

# makeCache(subviews:)

**实例方法**

为布局实例创建并初始化缓存。

## 声明

```swift
func makeCache(subviews: Self.Subviews) -> Self.Cache
```

## 参数

- **subviews**：代理实例集合，这些代理实例代表容器排列的视图。在计算要存储到缓存中的值时，可以使用集合中的代理来获取有关子视图的信息。

## 返回值

自定义布局容器方法之间共享的计算数据存储空间。

## 讨论

您可以选择使用缓存，在调用布局容器的方法时保留计算值。许多布局类型不需要缓存，因为 SwiftUI 会自动重用调用布局的结果以及布局从其子视图读取的值。如果不需要缓存，请使用此方法的协议默认实现。

但在以下情况下，您可能会发现缓存很有用

- 布局容器会在[sizeThatFits(proposal:subviews:cache:)](sizeThatFits_proposal_subviews_cache.zh-Hans.md)、[placeSubviews(in:proposal:subviews:cache:)](placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 和[explicitAlignment(of:in:proposal:subviews:cache:)](explicitAlignment_of_in_proposal_subviews_cache.zh-Hans.md) 等调用中重复进行复杂的中间计算。计算一次值并将其存储在缓存中也许能提高性能。
- 布局容器会从子视图中读取许多[LayoutValueKey](../LayoutValueKey.zh-Hans.md) 值。与其在每次布局调用前重新读取子视图的值，不如只读取一次并将结果存储到缓存中更有效率。
- 我们希望在调用布局时保持工作存储（如临时 Swift 数组），以尽量减少分配事件的数量。

只有在分析表明缓存可以提高性能时，才实施缓存。

### 初始化缓存

执行`makeCache(subviews:)` 方法来创建缓存。你可以使用`subviews` 输入参数中的信息，立即将计算值添加到缓存中，也可以稍后再添加。[Layout](../Layout.zh-Hans.md)协议中可以访问缓存的方法都将缓存作为输入输出参数，这样就可以在任何可以读取缓存的地方修改缓存。

您可以使用任何对您的布局算法有意义的存储类型，但请确保您只存储从布局及其子视图（如果可能的话，可采用懒惰方式）派生出来的数据。为使此方法正常工作，SwiftUI 需要能够调用此方法来重新创建缓存，而不改变布局结果。

从该方法返回缓存时，会隐式定义缓存的类型。请务必使其他`cache` 协议方法上的[Layout](../Layout.zh-Hans.md) 参数的类型相匹配，或者使用类型别名来定义[Cache](Cache.zh-Hans.md) 关联类型。

### 更新缓存

如果布局容器或其任何子视图发生变化，SwiftUI 会调用 [updateCache(_:subviews:)](updateCache___subviews.zh-Hans.md) 方法，以便您可以修改或废止缓存的内容。该方法的默认实现会调用 `makeCache(subviews:)`方法来重新创建缓存，但您也可以根据需要提供自己的 update 方法实现，以便采用增量方法。

## 管理缓存

- **updateCache(_:subviews:)**：当内容发生变化时更新布局的缓存。
- **Cache**：与布局实例相关联的缓存值。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/makeCache(subviews:)
crawled: 2025-12-02T17:53:10Z
---

# makeCache(subviews:)

**Instance Method**

Creates and initializes a cache for a layout instance.

## Declaration

```swift
func makeCache(subviews: Self.Subviews) -> Self.Cache
```

## Parameters

- **subviews**: A collection of proxy instances that represent the views that the container arranges. You can use the proxies in the collection to get information about the subviews as you calculate values to store in the cache.

## Return Value

Storage for calculated data that you share among the methods of your custom layout container.

## Discussion

You can optionally use a cache to preserve calculated values across calls to a layout container’s methods. Many layout types don’t need a cache, because SwiftUI automatically reuses both the results of calls into the layout and the values that the layout reads from its subviews. Rely on the protocol’s default implementation of this method if you don’t need a cache.

However you might find a cache useful when:

- The layout container repeats complex, intermediate calculations across calls like [sizeThatFits(proposal:subviews:cache:)](sizeThatFits_proposal_subviews_cache.zh-Hans.md), [placeSubviews(in:proposal:subviews:cache:)](placeSubviews_in_proposal_subviews_cache.zh-Hans.md), and [explicitAlignment(of:in:proposal:subviews:cache:)](explicitAlignment_of_in_proposal_subviews_cache.zh-Hans.md). You might be able to improve performance by calculating values once and storing them in a cache.
- The layout container reads many [LayoutValueKey](../LayoutValueKey.zh-Hans.md) values from subviews. It might be more efficient to do that once and store the results in the cache, rather than rereading the subviews’ values before each layout call.
- You want to maintain working storage, like temporary Swift arrays, across calls into the layout, to minimize the number of allocation events.

Only implement a cache if profiling shows that it improves performance.

### Initialize a cache

Implement the `makeCache(subviews:)` method to create a cache. You can add computed values to the cache right away, using information from the `subviews` input parameter, or you can do that later. The methods of the [Layout](../Layout.zh-Hans.md) protocol that can access the cache take the cache as an in-out parameter, which enables you to modify the cache anywhere that you can read it.

You can use any storage type that makes sense for your layout algorithm, but be sure that you only store data that you derive from the layout and its subviews (lazily, if possible). For this to work correctly, SwiftUI needs to be able to call this method to recreate the cache without changing the layout result.

When you return a cache from this method, you implicitly define a type for your cache. Be sure to either make the type of the `cache` parameters on your other [Layout](../Layout.zh-Hans.md) protocol methods match, or use a type alias to define the [Cache](Cache.zh-Hans.md) associated type.

### Update the cache

If the layout container or any of its subviews change, SwiftUI calls the [updateCache(_:subviews:)](updateCache___subviews.zh-Hans.md) method so you can modify or invalidate the contents of the cache. The default implementation of that method calls the `makeCache(subviews:)` method to recreate the cache, but you can provide your own implementation of the update method to take an incremental approach, if appropriate.

## Managing a cache

- **updateCache(_:subviews:)**: Updates the layout’s cache when something changes.
- **Cache**: Cached values associated with the layout instance.

