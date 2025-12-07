--- 来源：https://developer.apple.com/documentation/SwiftUI/View/exportsItemProviders(_:onExport:onEdit:)

抓取时间：2025-11-30T21:28:34Z

---

# exportsItemProviders(_:onExport:onEdit:)

**实例方法**

导出可供快捷指令、快速操作和服务使用的读写项提供程序。

## 声明

```swift
nonisolated func exportsItemProviders(_ contentTypes: [UTType], onExport: @escaping () -> [NSItemProvider], onEdit: @escaping ([NSItemProvider]) -> Bool) -> some View

```

## 参数

- **contentTypes**：视图支持导出和导入的内容类型。空数组表示视图当前不支持导出。

- **onExport**：快捷指令或服务请求项时将调用的闭包。

- **onEdit**：快捷指令或服务完成输出数据后将调用的闭包。此闭包应将导出的选定子部分替换为 `onExport`。返回 `false` 表示接收项目失败。

## 讨论

如果关联的视图支持选择，则导出的项目应反映所选子部分。

## 使用项目提供程序导入和导出

- **importsItemProviders(_:onImport:)**：启用从服务（例如 macOS 上的“连续互通相机”）导入项目提供程序。

- **exportsItemProviders(_:onExport:)**：导出只读项目提供程序，供快捷指令、快速操作和服务使用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/exportsItemProviders(_:onExport:onEdit:)
crawled: 2025-11-30T21:28:34Z
---

# exportsItemProviders(_:onExport:onEdit:)

**Instance Method**

Exports a read-write item provider for consumption by shortcuts, quick actions, and services.

## Declaration

```swift
nonisolated func exportsItemProviders(_ contentTypes: [UTType], onExport: @escaping () -> [NSItemProvider], onEdit: @escaping ([NSItemProvider]) -> Bool) -> some View

```

## Parameters

- **contentTypes**: The types of content that the view supports exporting and importing. An empty array means the view does not currently support exporting.
- **onExport**: A closure that will be called on request of the items by the shortcut or service.
- **onEdit**: A closure that will be called after the shortcut or service completes with its output data. This should replace the selected subpart that was exported with `onExport`. Return `false` to indicate that there was a failure to receive the items.

## Discussion

If the associated view supports selection, the exported item should reflect that selected subpart.

## Importing and exporting using item providers

- **importsItemProviders(_:onImport:)**: Enables importing item providers from services, such as Continuity Camera on macOS.
- **exportsItemProviders(_:onExport:)**: Exports a read-only item provider for consumption by shortcuts, quick actions, and services.

