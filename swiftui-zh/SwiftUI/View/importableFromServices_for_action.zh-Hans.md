--- 来源：https://developer.apple.com/documentation/SwiftUI/View/importableFromServices(for:action:)

抓取时间：2025-11-30T21:28:30Z

---

# importableFromServices(for:action:)

**实例方法**

允许从服务导入项目，例如 macOS 上的“连续互通相机”。

## 声明

```swift
nonisolated func importableFromServices<T>(for payloadType: T.Type = T.self, action: @escaping ([T]) -> Bool) -> some View where T : Transferable

```

## 参数

- **payloadType**：导入模型的预期类型。

- **action**：将使用导入的服务项目调用的闭包。返回 `false` 表示未能接收到项目。

## 讨论

```swift
@State private var title: String
var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .importableFromServices(for: String.self) { titles
            title = titles.first ?? title
            return !titles.isEmpty
        }
}
```

## 导入和导出可转移项目

- **exportableToServices(_:)**：导出可供快捷指令、快速操作和服务使用的项目。

- **exportableToServices(_:onEdit:)**：导出可供快捷指令、快速操作和服务使用的读写项目。


---
source: https://developer.apple.com/documentation/SwiftUI/View/importableFromServices(for:action:)
crawled: 2025-11-30T21:28:30Z
---

# importableFromServices(for:action:)

**Instance Method**

Enables importing items from services, such as Continuity Camera on macOS.

## Declaration

```swift
nonisolated func importableFromServices<T>(for payloadType: T.Type = T.self, action: @escaping ([T]) -> Bool) -> some View where T : Transferable

```

## Parameters

- **payloadType**: The expected type of the imported models.
- **action**: A closure that will be called with the imported service item. Return `false` to indicate that there was a failure to receive the items.

## Discussion

```swift
@State private var title: String
var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .importableFromServices(for: String.self) { titles
            title = titles.first ?? title
            return !titles.isEmpty
        }
}
```

## Importing and exporting transferable items

- **exportableToServices(_:)**: Exports items for consumption by shortcuts, quick actions, and services.
- **exportableToServices(_:onEdit:)**: Exports read-write items for consumption by shortcuts, quick actions, and services.

