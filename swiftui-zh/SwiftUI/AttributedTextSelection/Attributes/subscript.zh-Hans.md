---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/Attributes/subscript(_:)
抓取时间： 2025-12-04T13:17:11Z
---

# 下标(_:)

**实例下标**

返回迭代单个属性值的序列。

## 声明

```swift
subscript<K>(type: K.Type) -> some Sequence<Optional<K.Value>> where K : AttributedStringKey, K.Value : Sendable { get }
```

## 概览

在范围选择的情况下，返回的序列基于指定属性的运行，而不是所有属性的运行。

```swift
selection.attributes(in: text)[MyAttribute.self].contains(myValue)
```


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/Attributes/subscript(_:)
crawled: 2025-12-04T13:17:11Z
---

# subscript(_:)

**Instance Subscript**

Returns a sequence which iterates of the values of a single attribute.

## Declaration

```swift
subscript<K>(type: K.Type) -> some Sequence<Optional<K.Value>> where K : AttributedStringKey, K.Value : Sendable { get }
```

## Overview

In the case of a range selection, the returned sequence is based on the runs of the specified attribute, not the runs over all attributes.

```swift
selection.attributes(in: text)[MyAttribute.self].contains(myValue)
```

