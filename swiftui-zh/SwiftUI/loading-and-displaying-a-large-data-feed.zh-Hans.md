--- 来源：https://developer.apple.com/documentation/swiftui/loading-and-displaying-a-large-data-feed

抓取时间：2025-12-02T18:48:04Z

---

# 加载和显示大型数据源

**示例代码**

在后台处理数据，并通过批量导入和防止重复记录来降低内存使用量。

## 概述

此示例创建一个应用程序，该应用程序使用美国地质调查局 (USGS) 的实时数据源，显示过去 30 天内美国记录的地震列表。

要加载 USGS JSON 数据源，请执行以下任一操作：

- 在 iOS 上，下拉刷新 [List](List.zh-Hans.md)。

- 在 iOS 和 macOS 上，按下刷新按钮 (⌘R)。

应用会将请求的数据加载到默认委托队列 [doc://com.apple.documentation/documentation/Foundation/URLSession] 中，这是一个在后台运行的操作队列。在信息流下载完成且会话数据任务完成后，应用会继续处理此队列，将大量信息流元素导入到数据存储中，而不会阻塞主队列。

### 后台导入数据

要在后台导入数据，应用可以使用一个或两个托管对象上下文。示例使用了两个实例 ([doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext])：

- 一个主队列上下文，用于向用户界面提供数据。

- 一个私有队列上下文，用于在后台队列上执行导入操作。

这两个上下文都连接到同一个 [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/persistentStoreCoordinator]。这种配置比使用嵌套上下文更高效。

该示例通过使用 [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer] 设置 Core Data 堆栈来创建主队列上下文，该堆栈在其 [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] 属性中初始化主队列上下文。

```swift
let container = NSPersistentContainer(name: "Earthquakes")
```

通过调用持久容器的 [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/newBackgroundContext()] 方法创建私有队列上下文。

```swift
let taskContext = container.newBackgroundContext()
```

当 feed 下载完成后，该示例使用任务上下文在后台消费 feed。在 Core Data 中，每个基于队列的上下文都有自己的串行队列，应用程序必须通过将操作上下文的任务包装在 [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext/perform(_:)]（带或不带 `await` 关键字）或 [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext/performAndWait(_:)-ypye] 闭包中来序列化该队列。

```swift
try await taskContext.perform {
```

有关并发处理的更多信息，请参阅 [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext#Concurrency]。

为了高效处理大型数据集，示例使用了 [doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest]，它直接访问存储，无需与上下文交互、触发任何键值观察或分配托管对象。[doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] 的闭包式初始化器允许应用程序在 Core Data 调用 `dictionaryHandler` 闭包时一次提供一条记录，这有助于应用程序保持较低的内存占用，因为它们无需为所有记录准备缓冲区。

```swift
let batchInsertRequest = self.newBatchInsertRequest(with: propertiesList)
if let fetchResult = try? taskContext.execute(batchInsertRequest),
   let batchInsertResult = fetchResult as? NSBatchInsertResult,
   let success = batchInsertResult.result as? Bool, success {
    return
}
```

### 合并更改并更新用户界面

由于 [doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] 会绕过上下文，不会触发 [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContextDidSaveNotification] 通知，因此需要使用更改更新用户界面的应用有两种选择：

- 通过解析 store 的 [doc://com.apple.documentation/documentation/CoreData/persistent-history] 提取相关更改，然后将其合并到视图上下文中。有关持久历史记录跟踪的更多信息，请参阅 [doc://com.apple.documentation/documentation/CoreData/consuming-relevant-store-changes]。

- 从 store 重新获取数据。但是，如果视图上下文绑定到查询生成，则在获取数据之前需要重置上下文。有关查询生成的更多信息，请参阅 [doc://com.apple.documentation/documentation/CoreData/accessing-data-when-the-store-changes]。

此示例使用持久存储远程更改通知和持久历史记录跟踪来更新 UI，原因如下：

- 数据模型包含单个实体，因此所有更改都与 `List` 相关，无需解析历史记录中的特定更改。

- [FetchRequest](FetchRequest.zh-Hans.md) 直接从存储中获取和检索结果，`List` 会自动刷新其内容。

- SwiftUI 只关注视图上下文，因此 `QuakesProvider` 会监听 [doc://com.apple.documentation/documentation/Foundation/NSNotification/Name-swift.struct/NSPersistentStoreRemoteChange] 通知，将后台上下文中的更改合并到视图上下文中，执行批量操作。

要为持久存储启用远程更改通知，请将存储描述中的 [doc://com.apple.documentation/documentation/CoreData/NSPersistentStoreRemoteChangeNotificationPostOptionKey] 选项设置为 `true`。

```swift
description.setOption(true as NSNumber,
                      forKey: NSPersistentStoreRemoteChangeNotificationPostOptionKey)
```

通过将 [doc://com.apple.documentation/documentation/CoreData/NSPersistentHistoryTrackingKey] 选项同时设置为 `true`，为持久化存储启用持久化历史记录跟踪。

```swift
description.setOption(true as NSNumber,
                      forKey: NSPersistentHistoryTrackingKey)
```

当持久化存储发生更改时（包括其他进程的写入操作），存储会发出远程更改通知。示例程序收到通知后，会获取给定令牌之后发生的持久化历史记录事务和更改。持久化历史记录更改请求检索到历史记录后，示例程序会通过 [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext/mergeChanges(fromContextDidSave:)] 将每个事务的 [doc://com.apple.documentation/documentation/CoreData/NSPersistentHistoryTransaction/objectIDNotification()] 合并到视图上下文中。

```swift
let changeRequest = NSPersistentHistoryChangeRequest.fetchHistory(after: lastToken)
let historyResult = try taskContext.execute(changeRequest) as? NSPersistentHistoryResult
if let history = historyResult?.result as? [NSPersistentHistoryTransaction] {
    return history
}
```

执行每个 [doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] 或 [doc://com.apple.documentation/documentation/CoreData/NSBatchDeleteRequest] 后，示例程序会将所有 UI 更新分发回主队列，以便在 SwiftUI 中渲染它们。 ```swift
let viewContext = container.viewContext
let tokens = await viewContext.perform {
    history.map { (transaction: NSPersistentHistoryTransaction) -> NSPersistentHistoryToken in
        viewContext.mergeChanges(fromContextDidSave: transaction.objectIDNotification())
        return transaction.token
    }
}
```

合并上次事务的更改后，示例需要将令牌存储在内存或磁盘中，以便在后续的持久化历史记录更改请求中使用它。

### 批量处理以降低内存占用

当应用在上下文中获取或创建对象时，Core Data 会缓存该对象，以避免应用再次使用这些对象时往返于存储文件。然而，随着应用处理的对象越来越多，这种方法会增加应用的内存占用，最终可能导致 iOS 系统出现内存不足警告或应用终止。[doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] 不会明显增加应用的内存占用，因为它不会将数据加载到内存中。

示例将 `viewContext` 的 [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext/automaticallyMergesChangesFromParent] 属性设置为 `false`，以防止 Core Data 在每次保存后台上下文时自动合并更改。

```swift
container.viewContext.automaticallyMergesChangesFromParent = false
```

### 防止数据存储中出现重复数据

每次示例应用重新加载 JSON 数据源时，解析后的数据都包含过去一个月的所有地震记录，因此可能会出现大量已导入数据的重复项。为了避免创建重复记录，应用会约束一个属性或属性组合，使其在所有实例中保持唯一。

`code` 属性用于唯一标识一条地震记录，因此将 `Quake` 实体约束在 `code` 上，可以确保没有两条存储的记录具有相同的 `code` 值。

在数据模型编辑器中选择 `Quake` 实体。在数据模型检查器中，单击“约束”列表下的“+”按钮添加新约束。此时将显示一个约束占位符。

```swift
comma, separated, properties
```

双击占位符进行编辑。输入属性名称，或以逗号分隔的属性列表，作为实体的唯一约束。

```swift
code
```

保存新记录时，存储现在会检查是否存在已存在记录，且该记录的约束属性值相同。如果存在冲突，则会应用 [doc://com.apple.documentation/documentation/CoreData/NSMergeByPropertyObjectTrumpMergePolicy] 策略，新记录将覆盖现有记录中的所有字段。

```swift
container.viewContext.automaticallyMergesChangesFromParent = false
```

## 访问 Core Data

- **managedObjectContext**

- **FetchRequest**：一种属性包装类型，用于从 Core Data 持久存储中检索实体。

- **FetchedResults**：从 Core Data 存储中检索的结果集合。

- **SectionedFetchRequest**：一种属性包装类型，用于从 Core Data 持久化存储中检索按部分分组的实体。

- **SectionedFetchResults**：从 Core Data 持久化存储中检索并按部分分组的结果集合。


---
source: https://developer.apple.com/documentation/swiftui/loading-and-displaying-a-large-data-feed
crawled: 2025-12-02T18:48:04Z
---

# Loading and displaying a large data feed

**Sample Code**

Consume data in the background, and lower memory use by batching imports and preventing duplicate records.

## Overview

This sample creates an app that shows a list of earthquakes recorded in the United States in the past 30 days by consuming a U. S. Geological Survey (USGS) real-time data feed.

To load the USGS JSON feed, perform either of the following:

- On iOS, pull to refresh the [List](List.zh-Hans.md).
- On both iOS and macOS, press the refresh button (⌘R).

The app will load the requested data on the default delegate queue of [doc://com.apple.documentation/documentation/Foundation/URLSession], which is an operation queue that runs in the background. After the feed is downloaded and the session data task completes, the app continues working on this queue to import the large number of feed elements to the store without blocking the main queue.



### Import data in the background

To import data in the background, apps may use one or two managed object contexts. The sample uses two ([doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext]) instances:

- A main queue context to provide data to the user interface.
- A private queue context to perform the import on a background queue.

Both contexts are connected to the same [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/persistentStoreCoordinator]. This configuration is more efficient than using a nested context.

The sample creates a main queue context by setting up a Core Data stack using [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer], which initializes a main queue context in its [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] property.

```swift
let container = NSPersistentContainer(name: "Earthquakes")
```

Create a private queue context by calling the persistent container’s [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/newBackgroundContext()] method.

```swift
let taskContext = container.newBackgroundContext()
```

When the feed download finishes, the sample uses the task context to consume the feed in the background. In Core Data, every queue-based context has its own serial queue, and apps must serialize the tasks that manipulate the context with the queue by wrapping the code with a [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext/perform(_:)] — with or without the `await` keyword — or [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext/performAndWait(_:)-ypye] closure.

```swift
try await taskContext.perform {
```

For more information about working with concurrency, see [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext#Concurrency].

To efficiently handle large data sets, the sample uses [doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] which accesses the store directly — without interacting with the context, triggering any key value observation, or allocating managed objects. The closure-style initializer of [doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] allows apps to provide one record at a time when Core Data calls the `dictionaryHandler` closure, which helps apps keep their memory footprint low because they do not need to prepare a buffer for all records.

```swift
let batchInsertRequest = self.newBatchInsertRequest(with: propertiesList)
if let fetchResult = try? taskContext.execute(batchInsertRequest),
   let batchInsertResult = fetchResult as? NSBatchInsertResult,
   let success = batchInsertResult.result as? Bool, success {
    return
}
```

### Merge changes and update the user interface

Because [doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] bypasses the context and doesn’t trigger a [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContextDidSaveNotification] notification, apps that need to update the UI with the changes have two options:

- Extract the relevant changes by parsing the store’s [doc://com.apple.documentation/documentation/CoreData/persistent-history], then merge them into the view context. For more information on persistent history tracking, see [doc://com.apple.documentation/documentation/CoreData/consuming-relevant-store-changes].
- Re-fetch the data from the store. However, if the view context is pinned to a query generation, the context will need to be reset before fetching data. For more information on query generations, see [doc://com.apple.documentation/documentation/CoreData/accessing-data-when-the-store-changes].

This sample uses persistent store remote change notifications and persistent history tracking to update the UI, because:

- The data model contains a single entity, so all changes are relevant to the `List` and do not require parsing specific changes within the history.
- [FetchRequest](FetchRequest.zh-Hans.md) fetches and retrieves results directly from the store, and the `List` refreshes its contents automatically.
- SwiftUI is only concerned about the view context, so `QuakesProvider` observes the [doc://com.apple.documentation/documentation/Foundation/NSNotification/Name-swift.struct/NSPersistentStoreRemoteChange] notification to merge changes from the background context, performing the batch operations, into the view context.

Enable remote change notifications for a persistent store by setting the [doc://com.apple.documentation/documentation/CoreData/NSPersistentStoreRemoteChangeNotificationPostOptionKey] option on the store description to `true`.

```swift
description.setOption(true as NSNumber,
                      forKey: NSPersistentStoreRemoteChangeNotificationPostOptionKey)
```

Enable persistent history tracking for a persistent store by setting the [doc://com.apple.documentation/documentation/CoreData/NSPersistentHistoryTrackingKey] option to `true` as well.

```swift
description.setOption(true as NSNumber,
                      forKey: NSPersistentHistoryTrackingKey)
```

Whenever changes occur within a persistent store, including writes by other processes, the store posts a remote change notification. When the sample receives the notification, it fetches the persistent history transactions and changes occurring after a given token. After the persistent history change request retrieves the history, the sample merges each transaction’s [doc://com.apple.documentation/documentation/CoreData/NSPersistentHistoryTransaction/objectIDNotification()] into the view context via [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext/mergeChanges(fromContextDidSave:)].

```swift
let changeRequest = NSPersistentHistoryChangeRequest.fetchHistory(after: lastToken)
let historyResult = try taskContext.execute(changeRequest) as? NSPersistentHistoryResult
if let history = historyResult?.result as? [NSPersistentHistoryTransaction] {
    return history
}
```

After executing each [doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] or [doc://com.apple.documentation/documentation/CoreData/NSBatchDeleteRequest], the sample dispatches any UI updates back to the main queue, to render them in SwiftUI.

```swift
let viewContext = container.viewContext
let tokens = await viewContext.perform {
    history.map { (transaction: NSPersistentHistoryTransaction) -> NSPersistentHistoryToken in
        viewContext.mergeChanges(fromContextDidSave: transaction.objectIDNotification())
        return transaction.token
    }
}
```

After merging changes from the last transaction, the sample needs to store the token in memory or on disk, to use it in subsequent persistent history change requests.

### Work in batches to lower memory footprint

When apps fetch or create objects in a context, Core Data caches the object to avoid a round trip to the store file when the app uses those objects again. However, that approach grows the memory footprint of an app as it processes more and more objects, and can eventually lead to low-memory warnings or app termination on iOS. [doc://com.apple.documentation/documentation/CoreData/NSBatchInsertRequest] doesn’t obviously increase an app’s memory footprint because it doesn’t load data into memory.



The sample sets the `viewContext`’s [doc://com.apple.documentation/documentation/CoreData/NSManagedObjectContext/automaticallyMergesChangesFromParent] property to `false` to prevent Core Data from automatically merging changes every time the background context is saved.

```swift
container.viewContext.automaticallyMergesChangesFromParent = false
```

### Prevent duplicate data in the store

Every time the sample app reloads the JSON feed, the parsed data contains all earthquake records for the past month, so it can have many duplicates of already imported data. To avoid creating duplicate records, the app constrains an attribute, or combination of attributes, to be unique across all instances.

The `code` attribute uniquely identifies an earthquake record, so constraining the `Quake` entity on `code` ensures that no two stored records have the same `code` value.

Select the `Quake` entity in the data model editor. In the data model inspector, add a new constraint by clicking the + button under the Constraints list. A constraint placeholder appears.

```swift
comma, separated, properties
```

Double-click the placeholder to edit it. Enter the name of the attribute, or comma-separated list of attributes, to serve as unique constraints on the entity.

```swift
code
```

When saving a new record, the store now checks whether any record already exists with the same value for the constrained attribute. In the case of a conflict, an [doc://com.apple.documentation/documentation/CoreData/NSMergeByPropertyObjectTrumpMergePolicy] policy comes into play, and the new record overwrites all fields in the existing record.

```swift
container.viewContext.automaticallyMergesChangesFromParent = false
```

## Accessing Core Data

- **managedObjectContext**
- **FetchRequest**: A property wrapper type that retrieves entities from a Core Data persistent store.
- **FetchedResults**: A collection of results retrieved from a Core Data store.
- **SectionedFetchRequest**: A property wrapper type that retrieves entities, grouped into sections, from a Core Data persistent store.
- **SectionedFetchResults**: A collection of results retrieved from a Core Data persistent store, grouped into sections.

