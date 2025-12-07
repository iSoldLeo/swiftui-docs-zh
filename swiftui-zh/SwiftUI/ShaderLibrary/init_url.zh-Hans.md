--- 来源：https://developer.apple.com/documentation/SwiftUI/ShaderLibrary/init(url:)

抓取时间：2025-12-03T06:34:07Z

---

# init(url:)

**Initializer**

根据 `url` 的内容创建一个新的 Metal 着色器库，`url` 必须是预编译 Metal 库的位置。从返回的库编译的函数仅在返回的库存在期间才会被缓存。

## 声明

```swift
init(url: URL)
```

## 创建着色器库

- **init(data:)**：根据 `data` 的内容创建一个新的 Metal 着色器库，`data` 必须是预编译 Metal 库的内容。从返回的库编译的函数仅在返回的库存在期间才会被缓存。


---
source: https://developer.apple.com/documentation/SwiftUI/ShaderLibrary/init(url:)
crawled: 2025-12-03T06:34:07Z
---

# init(url:)

**Initializer**

Creates a new Metal shader library from the contents of `url`, which must be the location  of precompiled Metal library. Functions compiled from the returned library will only be cached as long as the returned library exists.

## Declaration

```swift
init(url: URL)
```

## Creating a shader library

- **init(data:)**: Creates a new Metal shader library from `data`, which must be the contents of precompiled Metal library. Functions compiled from the returned library will only be cached as long as the returned library exists.

