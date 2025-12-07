---
来源： https://developer.apple.com/documentation/swiftui/sectionedfetchrequest/update()
抓取时间： 2025-12-01T14:48:44Z
---

# update()

**实例方法**

更新获取的结果。

## 声明

```swift
@MainActor @preconcurrency func update()
```

## 讨论

SwiftUI 在渲染视图的[body-8kl5o](../View/body-8kl5o.zh-Hans.md)之前会调用此函数，以确保视图有最新的获取结果。

## 获取获取的结果

- **wrappedValue**：获取请求的提取结果。


---
source: https://developer.apple.com/documentation/swiftui/sectionedfetchrequest/update()
crawled: 2025-12-01T14:48:44Z
---

# update()

**Instance Method**

Updates the fetched results.

## Declaration

```swift
@MainActor @preconcurrency func update()
```

## Discussion

SwiftUI calls this function before rendering a view’s [body-8kl5o](../View/body-8kl5o.zh-Hans.md) to ensure the view has the most recent fetched results.

## Getting the fetched results

- **wrappedValue**: The fetched results of the fetch request.

