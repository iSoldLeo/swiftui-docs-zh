--- 来源：https://developer.apple.com/documentation/SwiftUI/ShaderLibrary/init(data:)

抓取时间：2025-12-03T06:34:08Z

---

# init(data:)

**Initializer**

从 `data` 创建一个新的 Metal 着色器库，`data` 必须是预编译 Metal 库的内容。从返回的库编译的函数仅在返回的库存在期间才会被缓存。

## 声明

```swift
init(data: Data)
```

## 创建着色器库

- **init(url:)**：从 `url` 的内容创建一个新的 Metal 着色器库，`url` 必须是预编译 Metal 库的位置。从返回的库编译的函数仅在返回的库存在期间才会被缓存。


---
source: https://developer.apple.com/documentation/SwiftUI/ShaderLibrary/init(data:)
crawled: 2025-12-03T06:34:08Z
---

# init(data:)

**Initializer**

Creates a new Metal shader library from `data`, which must be the contents of precompiled Metal library. Functions compiled from the returned library will only be cached as long as the returned library exists.

## Declaration

```swift
init(data: Data)
```

## Creating a shader library

- **init(url:)**: Creates a new Metal shader library from the contents of `url`, which must be the location  of precompiled Metal library. Functions compiled from the returned library will only be cached as long as the returned library exists.

