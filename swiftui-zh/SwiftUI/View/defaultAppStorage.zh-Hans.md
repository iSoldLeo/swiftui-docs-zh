--- 来源：https://developer.apple.com/documentation/SwiftUI/View/defaultAppStorage(_:)

抓取时间：2025-12-02T16:16:35Z

---

# defaultAppStorage(_:)

**实例方法**

视图中包含的 `AppStorage` 使用的默认存储。

## 声明

```swift
nonisolated func defaultAppStorage(_ store: UserDefaults) -> some View

```

## 参数

- **store**：用户默认将其用作 `AppStorage` 的默认存储。

## 讨论

如果未指定，则视图层次结构的默认存储为 `UserDefaults.standard`，但可以设置为自定义存储。例如，在应用和扩展程序之间共享默认值可以将默认存储覆盖为使用 `UserDefaults.init(suiteName:_)` 创建的存储。

## 跨应用启动保存状态

- **使用 SwiftUI 恢复应用状态**：通过保留用户当前活动，为用户提供应用连续性。

- **AppStorage**：一种属性包装类型，它反映 `UserDefaults` 中的值，并在该用户默认值发生更改时使视图失效。

- **SceneStorage**：一种属性包装类型，用于读取和写入持久化的、按场景存储。


---
source: https://developer.apple.com/documentation/SwiftUI/View/defaultAppStorage(_:)
crawled: 2025-12-02T16:16:35Z
---

# defaultAppStorage(_:)

**Instance Method**

The default store used by `AppStorage` contained within the view.

## Declaration

```swift
nonisolated func defaultAppStorage(_ store: UserDefaults) -> some View

```

## Parameters

- **store**: The user defaults to use as the default store for `AppStorage`.

## Discussion

If unspecified, the default store for a view hierarchy is `UserDefaults.standard`, but can be set a to a custom one. For example, sharing defaults between an app and an extension can override the default store to one created with `UserDefaults.init(suiteName:_)`.

## Saving state across app launches

- **Restoring your app’s state with SwiftUI**: Provide app continuity for users by preserving their current activities.
- **AppStorage**: A property wrapper type that reflects a value from `UserDefaults` and invalidates a view on a change in value in that user default.
- **SceneStorage**: A property wrapper type that reads and writes to persisted, per-scene storage.

