---
来源：https://developer.apple.com/documentation/SwiftUI/SceneStorage/init(wrappedValue:_:store:)
抓取时间：2025-12-02T21:00:30Z
---

# init(wrappedValue:_:store:)

**Initializer**

创建可保存和恢复标签页边栏自定义设置的属性。

### 声明

```swift
init(wrappedValue: Value = TabViewCustomization(), _ key: String, store: UserDefaults? = nil) where Value == TabViewCustomization
```

## 参数

- **wrappedValue**：如果给定密钥的自定义功能不可用，则为默认值。
- **key**：用于保存和恢复值的键。

## 讨论

您可以使用 [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md)在 TabView 上设置此自定义。

选项卡视图自定义通常不会添加到 `SceneStorage`，而是存储在 `AppStorage`中，这样不同场景中的自定义就会保持一致。


---
source: https://developer.apple.com/documentation/SwiftUI/SceneStorage/init(wrappedValue:_:store:)
crawled: 2025-12-02T21:00:30Z
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
- **key**: A key used to save and restore the value.

## Discussion

You can set this customization on the TabView using [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md).

The tab view customization is typically not added to `SceneStorage`, but instead stored in `AppStorage` so the customizations are consistent across different scenes.

