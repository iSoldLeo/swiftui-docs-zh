--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollViewReader/init(content:)

抓取时间：2025-12-03T05:44:56Z

---

# init(content:)

**Initializer**

创建一个实例，该实例可以对其子滚动视图执行编程滚动操作。

## 声明

```swift
init(@ViewBuilder content: @escaping (ScrollViewProxy) -> Content)
```

## 参数

- **content**：读取器的内容，包含一个或多个滚动视图。此视图构建器接收一个 [ScrollViewProxy](../ScrollViewProxy.zh-Hans.md) 实例，您可以使用该实例执行滚动操作。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollViewReader/init(content:)
crawled: 2025-12-03T05:44:56Z
---

# init(content:)

**Initializer**

Creates an instance that can perform programmatic scrolling of its child scroll views.

## Declaration

```swift
init(@ViewBuilder content: @escaping (ScrollViewProxy) -> Content)
```

## Parameters

- **content**: The reader’s content, containing one or more scroll views. This view builder receives a [ScrollViewProxy](../ScrollViewProxy.zh-Hans.md) instance that you use to perform scrolling.

