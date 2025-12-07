---
来源： https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(makeContent:)
抓取时间： 2025-12-01T02:39:49Z
---

# init(makeContent:)

**Initializer**

创建窗口组。

## 声明

```swift
nonisolated init(@ViewBuilder makeContent: @escaping () -> Content)
```

## 参数

- **makeContent**：为组的每个实例创建内容的闭包。

## 讨论

窗口组使用给定视图作为模板来创建组中每个窗口的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(makeContent:)
crawled: 2025-12-01T02:39:49Z
---

# init(makeContent:)

**Initializer**

Creates a window group.

## Declaration

```swift
nonisolated init(@ViewBuilder makeContent: @escaping () -> Content)
```

## Parameters

- **makeContent**: A closure that creates the content for each instance of the group.

## Discussion

The window group uses the given view as a template to form the content of each window in the group.

