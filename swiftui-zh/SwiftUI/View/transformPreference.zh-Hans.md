--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transformPreference(_:_:)

抓取时间：2025-12-02T17:32:28Z

---

# transformPreference(_:_:)

**实例方法**

对偏好设置值应用转换。

## 声明

```swift
nonisolated func transformPreference<K>(_ key: K.Type = K.self, _ callback: @escaping (inout K.Value) -> Void) -> some View where K : PreferenceKey

```

## 设置偏好设置

- **preference(key:value:)**：设置给定偏好设置的值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/transformPreference(_:_:)
crawled: 2025-12-02T17:32:28Z
---

# transformPreference(_:_:)

**Instance Method**

Applies a transformation to a preference value.

## Declaration

```swift
nonisolated func transformPreference<K>(_ key: K.Type = K.self, _ callback: @escaping (inout K.Value) -> Void) -> some View where K : PreferenceKey

```

## Setting preferences

- **preference(key:value:)**: Sets a value for the given preference.

