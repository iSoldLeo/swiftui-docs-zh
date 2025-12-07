---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingController/init(rootView:)
抓取时间： 2025-12-01T11:39:36Z
---

# init(rootView:)

**Initializer**

创建封装指定 SwiftUI 视图的托管控制器对象。

## 声明

```swift
@MainActor @preconcurrency init(rootView: Content)
```

## 参数

- **rootView**：要使用托管视图控制器管理的 SwiftUI 视图层次结构的根视图。

## 创建托管控制器对象

- **init(coder:rootView:)**：从存档和指定的 SwiftUI 视图创建托管控制器对象。
- **init(coder:)**：根据指定存档的内容创建托管控制器对象。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingController/init(rootView:)
crawled: 2025-12-01T11:39:36Z
---

# init(rootView:)

**Initializer**

Creates a hosting controller object that wraps the specified SwiftUI view.

## Declaration

```swift
@MainActor @preconcurrency init(rootView: Content)
```

## Parameters

- **rootView**: The root view of the SwiftUI view hierarchy that you want to manage using the hosting view controller.

## Creating a hosting controller object

- **init(coder:rootView:)**: Creates a hosting controller object from an archive and the specified SwiftUI view.
- **init(coder:)**: Creates a hosting controller object from the contents of the specified archive.

