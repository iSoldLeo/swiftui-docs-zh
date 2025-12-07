--- 来源：https://developer.apple.com/documentation/SwiftUI/View/exportableToServices(_:onEdit:)

抓取时间：2025-11-30T21:28:32Z

---

# exportableToServices(_:onEdit:)

**实例方法**

导出可供快捷指令、快速操作和服务使用的读写项。

## 声明

```swift
nonisolated func exportableToServices<T>(_ payload: @autoclosure @escaping () -> [T], onEdit: @escaping ([T]) -> Bool) -> some View where T : Transferable

```

## 参数

- **payload**：快捷指令或服务请求项时将调用的闭包。

- **onEdit**：快捷指令或服务完成输出数据后将调用的闭包。此闭包应替换已导出的选定子部分（`onExport`）。返回 `false` 表示未能成功接收项目。

## 讨论

如果关联的视图支持选择，则导出的项目应反映所选子部分。

```swift
@State private var title: String
var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .exportableToServices([title]) { editedTitles
            title = editedTitles.first ?? title
            return !editedTitles.isEmpty
        }
}
```

## 导入和导出可传输项目

- **importableFromServices(for:action:)**：启用从服务（例如 macOS 上的“连续互通相机”）导入项目。

- **exportableToServices(_:)**：导出项目以供快捷指令、快速操作和服务使用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/exportableToServices(_:onEdit:)
crawled: 2025-11-30T21:28:32Z
---

# exportableToServices(_:onEdit:)

**Instance Method**

Exports read-write items for consumption by shortcuts, quick actions, and services.

## Declaration

```swift
nonisolated func exportableToServices<T>(_ payload: @autoclosure @escaping () -> [T], onEdit: @escaping ([T]) -> Bool) -> some View where T : Transferable

```

## Parameters

- **payload**: A closure that will be called on request of the items by the shortcut or service.
- **onEdit**: A closure that will be called after the shortcut or service completes with its output data. This should replace the selected subpart that was exported with `onExport`. Return `false` to indicate that there was a failure to receive the items.

## Discussion

If the associated view supports selection, the exported item should reflect that selected subpart.

```swift
@State private var title: String
var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .exportableToServices([title]) { editedTitles
            title = editedTitles.first ?? title
            return !editedTitles.isEmpty
        }
}
```

## Importing and exporting transferable items

- **importableFromServices(for:action:)**: Enables importing items from services, such as Continuity Camera on macOS.
- **exportableToServices(_:)**: Exports items for consumption by shortcuts, quick actions, and services.

