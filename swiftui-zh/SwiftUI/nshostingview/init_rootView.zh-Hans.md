--- 来源：https://developer.apple.com/documentation/swiftui/nshostingview/init(rootview:)

抓取时间：2025-12-04T13:40:44Z

---

# init(rootView:)

**Initializer**

创建一个宿主视图对象，用于包装指定的 SwiftUI 视图。

## 声明

```swift
@MainActor @preconcurrency required init(rootView: Content)
```

## 参数

- **rootView**：要使用此宿主视图管理的 SwiftUI 视图层次结构的根视图。

## 创建宿主视图

- **init(coder:)**：从指定归档的内容创建宿主视图对象。

- **prepareForReuse()**


---
source: https://developer.apple.com/documentation/swiftui/nshostingview/init(rootview:)
crawled: 2025-12-04T13:40:44Z
---

# init(rootView:)

**Initializer**

Creates a hosting view object that wraps the specified SwiftUI view.

## Declaration

```swift
@MainActor @preconcurrency required init(rootView: Content)
```

## Parameters

- **rootView**: The root view of the SwiftUI view hierarchy that you want to manage using this hosting view.

## Creating a hosting view

- **init(coder:)**: Creates a hosting view object from the contents of the specified archive.
- **prepareForReuse()**

