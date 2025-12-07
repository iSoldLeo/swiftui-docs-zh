---
来源： https://developer.apple.com/documentation/SwiftUI/Persistent-storage
抓取时间： 2025-12-02T17:32:19Z
---

# 持久存储

**API 集合**

存储数据，供应用程序跨会话使用。

## 概览

操作系统提供了在应用程序关闭时存储数据的方法，这样当人们稍后再次打开应用程序时，就可以继续工作而不会中断。您所使用的机制取决于您需要存储的内容和数量、需要序列化还是随机访问数据等因素。



在 SwiftUI 应用程序中使用的存储方式与在其他应用程序中使用的相同。例如，您可以使用[doc://com.apple.documentation/documentation/Foundation/FileManager] 接口访问磁盘上的文件。不过，SwiftUI 还提供了一些便利，让您可以在声明式环境中更轻松地使用某些类型的持久化存储。例如，您可以使用 [FetchRequest](FetchRequest.zh-Hans.md) 和 [FetchedResults](FetchedResults.zh-Hans.md) 与核心数据模型交互。

## 在应用程序启动时保存状态

- 使用 SwiftUI 恢复应用程序的状态**：通过保留用户的当前活动，为用户提供应用程序的连续性。
- **defaultAppStorage(_:)**：视图中包含的`AppStorage`所使用的默认存储。
- **AppStorage**：一种属性包装类型，可反映`UserDefaults` 中的值，并在该用户默认值发生变化时使视图失效。
- **SceneStorage**：一种属性包装器类型，可读写持久化、按场景存储的内容。

## 访问核心数据

- 加载并显示大型数据源**：在后台消耗数据，并通过批量导入和防止重复记录来降低内存使用。
- **managedObjectContext**
- **FetchRequest**：属性包装器类型，用于从 Core Data 持久化存储中检索实体。
- **FetchedResults**：从 Core Data 存储检索结果的集合。
- **SectionedFetchRequest**：属性包装器类型，用于从核心数据持久性存储中检索按部分分组的实体。
- **SectionedFetchResults**：从核心数据持久性存储中检索的结果集合，按部分分组。

### 数据和存储

- 模型数据**：管理应用程序用于驱动其界面的数据。
- **环境值**：使用环境在整个视图层次结构中共享数据。
- **Preferences**：显示从视图到其容器视图的配置偏好。


---
source: https://developer.apple.com/documentation/SwiftUI/Persistent-storage
crawled: 2025-12-02T17:32:19Z
---

# Persistent storage

**API Collection**

Store data for use across sessions of your app.

## Overview

The operating system provides ways to store data when your app closes, so that when people open your app again later, they can continue working without interruption. The mechanism that you use depends on factors like what and how much you need to store, whether you need serialized or random access to the data, and so on.



You use the same kinds of storage in a SwiftUI app that you use in any other app. For example, you can access files on disk using the [doc://com.apple.documentation/documentation/Foundation/FileManager] interface. However, SwiftUI also provides conveniences that make it easier to use certain kinds of persistent storage in a declarative environment. For example, you can use [FetchRequest](FetchRequest.zh-Hans.md) and [FetchedResults](FetchedResults.zh-Hans.md) to interact with a Core Data model.

## Saving state across app launches

- **Restoring your app’s state with SwiftUI**: Provide app continuity for users by preserving their current activities.
- **defaultAppStorage(_:)**: The default store used by `AppStorage` contained within the view.
- **AppStorage**: A property wrapper type that reflects a value from `UserDefaults` and invalidates a view on a change in value in that user default.
- **SceneStorage**: A property wrapper type that reads and writes to persisted, per-scene storage.

## Accessing Core Data

- **Loading and displaying a large data feed**: Consume data in the background, and lower memory use by batching imports and preventing duplicate records.
- **managedObjectContext**
- **FetchRequest**: A property wrapper type that retrieves entities from a Core Data persistent store.
- **FetchedResults**: A collection of results retrieved from a Core Data store.
- **SectionedFetchRequest**: A property wrapper type that retrieves entities, grouped into sections, from a Core Data persistent store.
- **SectionedFetchResults**: A collection of results retrieved from a Core Data persistent store, grouped into sections.

## Data and storage

- **Model data**: Manage the data that your app uses to drive its interface.
- **Environment values**: Share data throughout a view hierarchy using the environment.
- **Preferences**: Indicate configuration preferences from views to their container views.

