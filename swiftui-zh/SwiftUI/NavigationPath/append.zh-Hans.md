--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationPath/append(_:)

抓取时间：2025-12-03T05:59:19Z

---

# append(_:)

**实例方法**

将一个新的可编码值追加到此路径的末尾。

## 声明

```swift
mutating func append<V>(_ value: V) where V : Decodable, V : Encodable, V : Hashable
```

## 管理路径内容

- **isEmpty**：一个布尔值，指示此路径是否为空。

- **count**：此路径中的元素数量。

- **removeLast(_:)**：从此路径的末尾移除值。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationPath/append(_:)
crawled: 2025-12-03T05:59:19Z
---

# append(_:)

**Instance Method**

Appends a new codable value to the end of this path.

## Declaration

```swift
mutating func append<V>(_ value: V) where V : Decodable, V : Encodable, V : Hashable
```

## Managing path contents

- **isEmpty**: A Boolean that indicates whether this path is empty.
- **count**: The number of elements in this path.
- **removeLast(_:)**: Removes values from the end of this path.

