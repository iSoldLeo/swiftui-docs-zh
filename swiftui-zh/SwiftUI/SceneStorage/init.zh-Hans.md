---
来源： https://developer.apple.com/documentation/SwiftUI/SceneStorage/init(_:)
抓取时间： 2025-12-02T21:00:28Z
---

# init(_:)

**Initializer**

创建一个可保存和恢复可选布尔值的属性。

### 声明

```swift
init(_ key: String) where Value == Bool?
```

## 参数

- **key**：用于保存和恢复值的键。

## 讨论

如果没有还原值，默认为 nil

## 存储值

- **init(wrappedValue:_:)**：创建一个可以保存和恢复整数的属性，将其转换为`RawRepresentable` 数据类型。


---
source: https://developer.apple.com/documentation/SwiftUI/SceneStorage/init(_:)
crawled: 2025-12-02T21:00:28Z
---

# init(_:)

**Initializer**

Creates a property that can save and restore an Optional boolean.

## Declaration

```swift
init(_ key: String) where Value == Bool?
```

## Parameters

- **key**: A key used to save and restore the value.

## Discussion

Defaults to nil if there is no restored value

## Storing a value

- **init(wrappedValue:_:)**: Creates a property that can save and restore an integer, transforming it to a `RawRepresentable` data type.

