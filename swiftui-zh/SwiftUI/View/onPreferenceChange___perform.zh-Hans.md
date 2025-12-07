--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onPreferenceChange(_:perform:)

抓取时间：2025-11-30T21:17:36Z

---

# onPreferenceChange(_:perform:)

**实例方法**

添加一个操作，当指定的偏好设置键的值发生变化时执行。

## 声明

```swift
nonisolated func onPreferenceChange<K>(_ key: K.Type = K.self, perform action: @escaping (K.Value) -> Void) -> some View where K : PreferenceKey, K.Value : Equatable

```

## 参数

- **key**：要监视值变化的键。

- **action**：当 `key` 的值发生变化时要执行的操作。`action` 闭包会将新值作为参数传递。

## 返回值

当 `key` 的值发生变化时，触发 `action` 的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onPreferenceChange(_:perform:)
crawled: 2025-11-30T21:17:36Z
---

# onPreferenceChange(_:perform:)

**Instance Method**

Adds an action to perform when the specified preference key’s value changes.

## Declaration

```swift
nonisolated func onPreferenceChange<K>(_ key: K.Type = K.self, perform action: @escaping (K.Value) -> Void) -> some View where K : PreferenceKey, K.Value : Equatable

```

## Parameters

- **key**: The key to monitor for value changes.
- **action**: The action to perform when the value for `key` changes. The `action` closure passes the new value as its parameter.

## Return Value

A view that triggers `action` when the value for `key` changes.

