---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingController/init(coder:rootView:)
抓取时间： 2025-12-01T11:39:37Z
---

# init(coder:rootView:)

**Initializer**

从归档文件和指定的 SwiftUI 视图创建托管控制器对象。

## 声明

```swift
@MainActor @preconcurrency init?(coder: NSCoder, rootView: Content)
```

## 参数

- **coder**：初始化时要使用的解码器。
- **rootView**：要使用此视图控制器管理的 SwiftUI 视图层次结构的根视图。

## 创建托管控制器对象

- **init(rootView:)**：创建封装指定 SwiftUI 视图的托管控制器对象。
- **init(coder:)**：根据指定存档的内容创建托管控制器对象。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingController/init(coder:rootView:)
crawled: 2025-12-01T11:39:37Z
---

# init(coder:rootView:)

**Initializer**

Creates a hosting controller object from an archive and the specified SwiftUI view.

## Declaration

```swift
@MainActor @preconcurrency init?(coder: NSCoder, rootView: Content)
```

## Parameters

- **coder**: The decoder to use during initialization.
- **rootView**: The root view of the SwiftUI view hierarchy that you want to manage using this view controller.

## Creating a hosting controller object

- **init(rootView:)**: Creates a hosting controller object that wraps the specified SwiftUI view.
- **init(coder:)**: Creates a hosting controller object from the contents of the specified archive.

