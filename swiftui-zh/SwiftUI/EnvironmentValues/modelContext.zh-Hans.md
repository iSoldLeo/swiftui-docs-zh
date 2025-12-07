---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/modelContext
抓取时间： 2025-12-03T06:07:15Z
---

# modelContext

**实例属性**

SwiftData 模型上下文，用于在此环境中进行查询和其他模型操作。

## 声明

```swift
var modelContext: ModelContext { get set }
```

## 全局对象

- **calendar**：视图处理日期时应使用的当前日历。
- **documentConfiguration**：[DocumentGroup](../DocumentGroup.zh-Hans.md)中文档的配置。
- **locale**：视图应使用的当前语言。
- **managedObjectContext**：视图应使用的当前 locale。
- **timeZone**：视图处理日期时应使用的当前时区。
- **undoManager**：用于注册视图撤销操作的撤销管理器。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/modelContext
crawled: 2025-12-03T06:07:15Z
---

# modelContext

**Instance Property**

The SwiftData model context that will be used for queries and other model operations within this environment.

## Declaration

```swift
var modelContext: ModelContext { get set }
```

## Global objects

- **calendar**: The current calendar that views should use when handling dates.
- **documentConfiguration**: The configuration of a document in a [DocumentGroup](../DocumentGroup.zh-Hans.md).
- **locale**: The current locale that views should use.
- **managedObjectContext**
- **timeZone**: The current time zone that views should use when handling dates.
- **undoManager**: The undo manager used to register a view’s undo operations.

