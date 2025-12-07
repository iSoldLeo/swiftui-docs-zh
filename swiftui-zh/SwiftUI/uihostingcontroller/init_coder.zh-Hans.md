---
来源：https://developer.apple.com/documentation/SwiftUI/UIHostingController/init(编码者：)
抓取时间： 2025-12-03T06:58:16Z
---

# init(coder:)

**Initializer**

根据指定压缩文件的内容创建托管控制器对象。

## 声明

```swift
@MainActor @preconcurrency required dynamic init?(coder aDecoder: NSCoder)
```

## 讨论

此方法的默认实现会引发异常。要从归档文件中创建视图控制器，请覆盖此方法，并使用 [init(coder:rootView:)](init_coder_rootView.zh-Hans.md) 方法初始化超类。

-参数编码器：初始化时使用的解码器。

## 创建托管控制器对象

- **init(rootView:)**：创建封装指定 SwiftUI 视图的托管控制器对象。
- **init(coder:rootView:)**：从归档和指定的 SwiftUI 视图创建托管控制器对象。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingController/init(coder:)
crawled: 2025-12-03T06:58:16Z
---

# init(coder:)

**Initializer**

Creates a hosting controller object from the contents of the specified archive.

## Declaration

```swift
@MainActor @preconcurrency required dynamic init?(coder aDecoder: NSCoder)
```

## Discussion

The default implementation of this method throws an exception. To create your view controller from an archive, override this method and initialize the superclass using the [init(coder:rootView:)](init_coder_rootView.zh-Hans.md) method instead.

-Parameter coder: The decoder to use during initialization.

## Creating a hosting controller object

- **init(rootView:)**: Creates a hosting controller object that wraps the specified SwiftUI view.
- **init(coder:rootView:)**: Creates a hosting controller object from an archive and the specified SwiftUI view.

