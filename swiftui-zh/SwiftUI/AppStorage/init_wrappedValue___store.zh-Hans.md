--- 来源：https://developer.apple.com/documentation/SwiftUI/AppStorage/init(wrappedValue:_:store:)

抓取时间：2025-12-01T00:44:06Z

---

# init(wrappedValue:_:store:)

**Initializer**

创建一个属性，用于保存和恢复标签页侧边栏的自定义设置。

## 声明

```swift
init(wrappedValue: Value = TabViewCustomization(), _ key: String, store: UserDefaults? = nil) where Value == TabViewCustomization
```

## 参数

- **wrappedValue**：如果给定键没有对应的自定义设置，则使用此默认值。

- **key**：用于在用户默认存储中读取和写入值的键。

- **store**：用于读取和写入的用户默认存储。 `nil` 的值将使用环境中的用户默认值。

## 讨论

您可以使用 [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md) 在 TabView 上设置此自定义项。

## 存储值

- **init(_:store:)**：创建一个可以读取和写入可选布尔值用户默认值的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/AppStorage/init(wrappedValue:_:store:)
crawled: 2025-12-01T00:44:06Z
---

# init(wrappedValue:_:store:)

**Initializer**

Creates a property that can save and restore tab sidebar customizations.

## Declaration

```swift
init(wrappedValue: Value = TabViewCustomization(), _ key: String, store: UserDefaults? = nil) where Value == TabViewCustomization
```

## Parameters

- **wrappedValue**: The default value if the customization is not available for the given key.
- **key**: The key to read and write the value to in the user defaults store.
- **store**: The user defaults store to read and write to. A value of `nil` will use the user default store from the environment.

## Discussion

You can set this customization on the TabView using [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md).

## Storing a value

- **init(_:store:)**: Creates a property that can read and write an Optional boolean user default.

