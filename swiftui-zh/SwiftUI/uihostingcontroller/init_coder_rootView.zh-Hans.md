---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingController/init(coder:rootView:)
抓取时间： 2025-12-01T11:47:27Z
---

# init(coder:rootView:)

**Initializer**

从归档文件和指定的 SwiftUI 视图创建托管控制器对象。

## 声明

```swift
@MainActor @preconcurrency init?(coder aDecoder: NSCoder, rootView: Content)
```

## 参数

- **rootView**：要使用此视图控制器管理的 SwiftUI 视图层次结构的根视图。

## 返回值

一个`UIViewController`对象，您可以通过您的界面展示该对象。

## 创建托管控制器对象

- **init(rootView:)**：创建封装指定 SwiftUI 视图的托管控制器对象。
- **init(coder:)**：根据指定存档的内容创建托管控制器对象。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingController/init(coder:rootView:)
crawled: 2025-12-01T11:47:27Z
---

# init(coder:rootView:)

**Initializer**

Creates a hosting controller object from an archive and the specified SwiftUI view.

## Declaration

```swift
@MainActor @preconcurrency init?(coder aDecoder: NSCoder, rootView: Content)
```

## Parameters

- **rootView**: The root view of the SwiftUI view hierarchy that you want to manage using this view controller.

## Return Value

A `UIViewController` object that you can present from your interface.

## Creating a hosting controller object

- **init(rootView:)**: Creates a hosting controller object that wraps the specified SwiftUI view.
- **init(coder:)**: Creates a hosting controller object from the contents of the specified archive.

