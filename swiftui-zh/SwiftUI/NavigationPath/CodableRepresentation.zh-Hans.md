--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationPath/CodableRepresentation
抓取时间：2025-12-03T05:59:22Z

---

# NavigationPath.CodableRepresentation

**Structure**

导航路径的可序列化表示。

## 声明

```swift
struct CodableRepresentation
```

## 概述

当导航路径包含符合 [doc://com.apple.documentation/documentation/Swift/Codable] 协议的元素时，可以使用路径的 `CodableRepresentation` 将路径转换为外部表示，以及将外部表示转换回导航路径。

## 路径编码

- **codable**：以可序列化格式描述此路径内容的值。

## 符合以下标准

- 可复制

- 可解码

- 可编码

- 可等值化


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationPath/CodableRepresentation
crawled: 2025-12-03T05:59:22Z
---

# NavigationPath.CodableRepresentation

**Structure**

A serializable representation of a navigation path.

## Declaration

```swift
struct CodableRepresentation
```

## Overview

When a navigation path contains elements the conform to the [doc://com.apple.documentation/documentation/Swift/Codable] protocol, you can use the path’s `CodableRepresentation` to convert the path to an external representation and to convert an external representation back into a navigation path.

## Encoding a path

- **codable**: A value that describes the contents of this path in a serializable format.

## Conforms To

- Copyable
- Decodable
- Encodable
- Equatable

