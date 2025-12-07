--- 来源：https://developer.apple.com/documentation/SwiftUI/AppStorage/init(_:store:)

抓取时间：2025-12-01T00:44:06Z

---

# init(_:store:)

**Initializer**

创建一个可以读取和写入可选布尔值用户默认值的属性。

## 声明

```swift
init(_ key: String, store: UserDefaults? = nil) where Value == Bool?
```

## 参数

- **key**：用于读取和写入用户默认值存储的键。

- **store**：要读取和写入的用户默认值存储。值为 `nil` 将使用环境变量中的用户默认值存储。

## 说明

如果没有恢复值，则默认为 nil。

## 存储值

- **init(wrappedValue:_:store:)**：创建一个属性，用于保存和恢复标签页侧边栏的自定义设置。


---
source: https://developer.apple.com/documentation/SwiftUI/AppStorage/init(_:store:)
crawled: 2025-12-01T00:44:06Z
---

# init(_:store:)

**Initializer**

Creates a property that can read and write an Optional boolean user default.

## Declaration

```swift
init(_ key: String, store: UserDefaults? = nil) where Value == Bool?
```

## Parameters

- **key**: The key to read and write the value to in the user defaults store.
- **store**: The user defaults store to read and write to. A value of `nil` will use the user default store from the environment.

## Discussion

Defaults to nil if there is no restored value.

## Storing a value

- **init(wrappedValue:_:store:)**: Creates a property that can save and restore tab sidebar customizations.

