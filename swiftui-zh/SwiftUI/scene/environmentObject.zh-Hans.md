--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/environmentObject(_:)

抓取时间：2025-11-30T21:17:19Z

---

# environmentObject(_:)

**实例方法**

向视图子层级提供 `ObservableObject`。

## 声明

```swift
nonisolated func environmentObject<T>(_ object: T) -> some Scene where T : ObservableObject

```

## 参数

- **object**：要存储并提供给场景子层级的对象。

## 讨论

任何子视图都可以使用 `EnvironmentObject` 读取该对象：

```swift
final class Profile: ObservableObject { ... }

@main
struct MyApp: App {
    var body: some View {
        WindowGroup {
            ContentView()
        }
        .environment(ProfileService.currentProfile)
    }
}
```

然后，您可以使用 [EnvironmentObject](../EnvironmentObject.zh-Hans.md) 属性包装器在 `ContentView` 或其后代视图中读取该对象：

```swift
struct ContentView: View {
    @EnvironmentObject private var currentAccount: Account

    var body: some View { ... }
}
```

## 在应用程序中分发模型数据

- **environmentObject(_:)**：向视图层次结构提供可观察对象。

- **EnvironmentObject**：父视图或祖先视图提供的可观察对象的属性包装器类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/environmentObject(_:)
crawled: 2025-11-30T21:17:19Z
---

# environmentObject(_:)

**Instance Method**

Supplies an `ObservableObject` to a view subhierarchy.

## Declaration

```swift
nonisolated func environmentObject<T>(_ object: T) -> some Scene where T : ObservableObject

```

## Parameters

- **object**: The object to store and make available to the scene’s subhierarchy.

## Discussion

The object can be read by any child by using `EnvironmentObject`:

```swift
final class Profile: ObservableObject { ... }

@main
struct MyApp: App {
    var body: some View {
        WindowGroup {
            ContentView()
        }
        .environment(ProfileService.currentProfile)
    }
}
```

You then read the object inside `ContentView` or one of its descendants using the [EnvironmentObject](../EnvironmentObject.zh-Hans.md) property wrapper:

```swift
struct ContentView: View {
    @EnvironmentObject private var currentAccount: Account

    var body: some View { ... }
}
```

## Distributing model data throughout your app

- **environmentObject(_:)**: Supplies an observable object to a view’s hierarchy.
- **EnvironmentObject**: A property wrapper type for an observable object that a parent or ancestor view supplies.

