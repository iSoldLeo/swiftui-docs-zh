---
来源： https://developer.apple.com/documentation/SwiftUI/AppStorage
抓取时间： 2025-12-02T16:16:36Z
---

# AppStorage

**Structure**

属性包装器类型，用于反映`UserDefaults` 中的值，并在用户默认值发生变化时使视图失效。

### 声明

```swift
@frozen @propertyWrapper struct AppStorage<Value>
```

## 存储值

- **init(wrappedValue:_:store:)**：创建一个可以保存和恢复选项卡侧边栏自定义设置的属性。
- **init(_:store:)**：创建一个可读写可选布尔用户默认值的属性。

## 获取值

- 获取值
- **projectedValue**

## 在应用程序启动时保存状态

- 使用 SwiftUI 恢复应用程序的状态**：通过保留用户的当前活动，为用户提供应用程序的连续性。
- **defaultAppStorage(_:)**：视图中包含的`AppStorage`所使用的默认存储。
- **SceneStorage**：一种属性包装器类型，用于读写持久化的每个场景存储。

## 符合

- 动态属性
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/AppStorage
crawled: 2025-12-02T16:16:36Z
---

# AppStorage

**Structure**

A property wrapper type that reflects a value from `UserDefaults` and invalidates a view on a change in value in that user default.

## Declaration

```swift
@frozen @propertyWrapper struct AppStorage<Value>
```

## Storing a value

- **init(wrappedValue:_:store:)**: Creates a property that can save and restore tab sidebar customizations.
- **init(_:store:)**: Creates a property that can read and write an Optional boolean user default.

## Getting the value

- **wrappedValue**
- **projectedValue**

## Saving state across app launches

- **Restoring your app’s state with SwiftUI**: Provide app continuity for users by preserving their current activities.
- **defaultAppStorage(_:)**: The default store used by `AppStorage` contained within the view.
- **SceneStorage**: A property wrapper type that reads and writes to persisted, per-scene storage.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

