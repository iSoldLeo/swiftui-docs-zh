--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationPath/codable
抓取时间：2025-12-03T05:59:21Z

---

# codable

**实例属性**

以可序列化格式描述此路径内容的值。

## 声明

```swift
var codable: NavigationPath.CodableRepresentation? { get }
```

## 说明

如果路径中任何类型擦除的元素不符合 [doc://com.apple.documentation/documentation/Swift/Codable] 协议，则此值为 `nil`。

## 路径编码

- **NavigationPath.CodableRepresentation**：导航路径的可序列化表示。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationPath/codable
crawled: 2025-12-03T05:59:21Z
---

# codable

**Instance Property**

A value that describes the contents of this path in a serializable format.

## Declaration

```swift
var codable: NavigationPath.CodableRepresentation? { get }
```

## Discussion

This value is `nil` if any of the type-erased elements of the path don’t conform to the [doc://com.apple.documentation/documentation/Swift/Codable] protocol.

## Encoding a path

- **NavigationPath.CodableRepresentation**: A serializable representation of a navigation path.

