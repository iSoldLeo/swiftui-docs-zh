--- 来源：https://developer.apple.com/documentation/SwiftUI/NSHostingView/init(coder:)

抓取时间：2025-12-01T11:39:56Z

---

# init(coder:)

**Initializer**

从指定归档的内容创建一个宿主视图对象。

## 声明

```swift
@MainActor @preconcurrency required dynamic init?(coder aDecoder: NSCoder)
```

## 讨论

此方法的默认实现会抛出异常。要从归档创建视图，请重写此方法，并使用 [init(coder:rootView:)](init_coder_rootView.zh-Hans.md) 方法初始化超类。

## 创建宿主视图

- **init(rootView:)**：创建一个包装指定 SwiftUI 视图的宿主视图对象。

- **prepareForReuse()**


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingView/init(coder:)
crawled: 2025-12-01T11:39:56Z
---

# init(coder:)

**Initializer**

Creates a hosting view object from the contents of the specified archive.

## Declaration

```swift
@MainActor @preconcurrency required dynamic init?(coder aDecoder: NSCoder)
```

## Discussion

The default implementation of this method throws an exception. To create your view from an archive, override this method and initialize the superclass using the [init(coder:rootView:)](init_coder_rootView.zh-Hans.md) method instead.

## Creating a hosting view

- **init(rootView:)**: Creates a hosting view object that wraps the specified SwiftUI view.
- **prepareForReuse()**

