--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transformEnvironment(_:transform:)

抓取时间：2025-11-30T21:17:29Z

---

# transformEnvironment(_:transform:)

**实例方法**

使用给定的函数转换指定键路径的环境值。

## 声明

```swift
nonisolated func transformEnvironment<V>(_ keyPath: WritableKeyPath<EnvironmentValues, V>, transform: @escaping (inout V) -> Void) -> some View

```

## 修改视图的环境

- **environment(_:)**：将一个可观察对象放置在视图的环境中。

- **environment(_:_:)**：将指定键路径的环境值设置为给定值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/transformEnvironment(_:transform:)
crawled: 2025-11-30T21:17:29Z
---

# transformEnvironment(_:transform:)

**Instance Method**

Transforms the environment value of the specified key path with the given function.

## Declaration

```swift
nonisolated func transformEnvironment<V>(_ keyPath: WritableKeyPath<EnvironmentValues, V>, transform: @escaping (inout V) -> Void) -> some View

```

## Modifying the environment of a view

- **environment(_:)**: Places an observable object in the view’s environment.
- **environment(_:_:)**: Sets the environment value of the specified key path to the given value.

