--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/defaultAppStorage(_:)

抓取时间：2025-12-03T05:31:03Z

---

# defaultAppStorage(_:)

**实例方法**

场景及其视图内容中 `AppStorage` 使用的默认存储。

## 声明

```swift
nonisolated func defaultAppStorage(_ store: UserDefaults) -> some Scene

```

## 参数

- **store**：用户默认将其用作 `AppStorage` 的默认存储。

## 讨论

如果未指定，则视图层级的默认存储为 `UserDefaults.standard`，但可以设置为自定义存储。例如，在应用和扩展程序之间共享默认设置可以将默认存储覆盖为使用 `UserDefaults.init(suiteName:_)` 创建的存储。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/defaultAppStorage(_:)
crawled: 2025-12-03T05:31:03Z
---

# defaultAppStorage(_:)

**Instance Method**

The default store used by `AppStorage` contained within the scene and its view content.

## Declaration

```swift
nonisolated func defaultAppStorage(_ store: UserDefaults) -> some Scene

```

## Parameters

- **store**: The user defaults to use as the default store for `AppStorage`.

## Discussion

If unspecified, the default store for a view hierarchy is `UserDefaults.standard`, but can be set a to a custom one. For example, sharing defaults between an app and an extension can override the default store to one created with `UserDefaults.init(suiteName:_)`.

