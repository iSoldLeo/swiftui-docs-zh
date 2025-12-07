--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/update()
抓取时间：2025-12-02T18:48:12Z

---

# update()

**实例方法**

更新已获取的结果。

## 声明

```swift
@MainActor @preconcurrency mutating func update()
```

## 说明

SwiftUI 会在渲染视图的 [body-8kl5o](../View/body-8kl5o.zh-Hans.md) 之前调用此函数，以确保视图拥有最新的已获取结果。

## 获取已获取的结果

- **wrappedValue**：获取请求的已获取结果。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/update()
crawled: 2025-12-02T18:48:12Z
---

# update()

**Instance Method**

Updates the fetched results.

## Declaration

```swift
@MainActor @preconcurrency mutating func update()
```

## Discussion

SwiftUI calls this function before rendering a view’s [body-8kl5o](../View/body-8kl5o.zh-Hans.md) to ensure the view has the most recent fetched results.

## Getting the fetched results

- **wrappedValue**: The fetched results of the fetch request.

