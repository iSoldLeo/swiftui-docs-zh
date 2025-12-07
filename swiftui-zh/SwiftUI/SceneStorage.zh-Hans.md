--- 来源：https://developer.apple.com/documentation/SwiftUI/SceneStorage
抓取时间：2025-12-02T16:16:37Z

---

# SceneStorage

**Structure**

一种属性包装类型，用于读写持久化的场景级存储。

## 声明

```swift
@frozen @propertyWrapper struct SceneStorage<Value>
```

## 概述

当需要自动恢复值状态时，可以使用 `SceneStorage`。`SceneStorage` 的工作方式与 `State` 非常相似，区别在于，如果之前已保存，则其初始值由系统恢复，并且该值与同一场景中的其他 `SceneStorage` 变量共享。

系统会代表您管理 `SceneStorage` 的保存和恢复。您无法直接访问 `SceneStorage` 的底层数据，因此必须通过 `SceneStorage` 属性包装器进行访问。系统不保证数据何时以及多久会持久化一次。

每个 `Scene` 都有其自身的 `SceneStorage` 概念，因此场景之间不会共享数据。

请确保您与 `SceneStorage` 一起使用的数据是轻量级的。大型数据（例如模型数据）不应存储在 `SceneStorage` 中，否则可能会导致性能下降。

如果显式销毁 `Scene`（例如，在 iPadOS 上销毁切换器快照或在 macOS 上关闭窗口），则数据也会被销毁。请勿将 `SceneStorage` 用于敏感数据。

## 存储值

- **init(wrappedValue:_:)**：创建一个属性，用于保存和恢复整数，并将其转换为 `RawRepresentable` 数据类型。

- **init(_:)**：创建一个属性，用于保存和恢复可选布尔值。

## 获取值

- **wrappedValue**：状态变量引用的底层值。

- **projectedValue**：状态值的绑定。

## 初始化器

- **init(wrappedValue:_:store:)**：创建一个属性，用于保存和恢复标签页侧边栏的自定义设置。

## 跨应用启动保存状态

- **使用 SwiftUI 恢复应用状态**：通过保留用户当前的活动，为用户提供应用的连续性。

- **defaultAppStorage(_:)**：视图中包含的 `AppStorage` 使用的默认存储。

- **AppStorage**：一个属性包装类型，它反映 `UserDefaults` 中的值，并在该用户默认值发生更改时使视图失效。

## 符合以下规范

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SceneStorage
crawled: 2025-12-02T16:16:37Z
---

# SceneStorage

**Structure**

A property wrapper type that reads and writes to persisted, per-scene storage.

## Declaration

```swift
@frozen @propertyWrapper struct SceneStorage<Value>
```

## Overview

You use `SceneStorage` when you need automatic state restoration of the value.  `SceneStorage` works very similar to `State`, except its initial value is restored by the system if it was previously saved, and the value is shared with other `SceneStorage` variables in the same scene.

The system manages the saving and restoring of `SceneStorage` on your behalf. The underlying data that backs `SceneStorage` is not available to you, so you must access it via the `SceneStorage` property wrapper. The system makes no guarantees as to when and how often the data will be persisted.

Each `Scene` has its own notion of `SceneStorage`, so data is not shared between scenes.

Ensure that the data you use with `SceneStorage` is lightweight. Data of a large size, such as model data, should not be stored in `SceneStorage`, as poor performance may result.

If the `Scene` is explicitly destroyed (e.g. the switcher snapshot is destroyed on iPadOS or the window is closed on macOS), the data is also destroyed. Do not use `SceneStorage` with sensitive data.

## Storing a value

- **init(wrappedValue:_:)**: Creates a property that can save and restore an integer, transforming it to a `RawRepresentable` data type.
- **init(_:)**: Creates a property that can save and restore an Optional boolean.

## Getting the value

- **wrappedValue**: The underlying value referenced by the state variable.
- **projectedValue**: A binding to the state value.

## Initializers

- **init(wrappedValue:_:store:)**: Creates a property that can save and restore tab sidebar customizations.

## Saving state across app launches

- **Restoring your app’s state with SwiftUI**: Provide app continuity for users by preserving their current activities.
- **defaultAppStorage(_:)**: The default store used by `AppStorage` contained within the view.
- **AppStorage**: A property wrapper type that reflects a value from `UserDefaults` and invalidates a view on a change in value in that user default.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

