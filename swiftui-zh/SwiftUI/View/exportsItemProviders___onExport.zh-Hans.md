--- 来源：https://developer.apple.com/documentation/SwiftUI/View/exportsItemProviders(_:onExport:)

抓取时间：2025-12-02T17:43:34Z

---

# exportsItemProviders(_:onExport:)

**实例方法**

导出只读项提供程序，供快捷指令、快速操作和服务使用。

## 声明

```swift
nonisolated func exportsItemProviders(_ contentTypes: [UTType], onExport: @escaping () -> [NSItemProvider]) -> some View

```

## 参数

- **contentTypes**：视图支持导出的内容类型。空数组表示视图当前不支持导出。

- **onExport**：快捷指令或服务请求项时将调用的闭包。

## 说明

如果关联的视图支持选择，则导出的项应反映所选的子部分。

## 使用项目提供程序导入和导出

- **importsItemProviders(_:onImport:)**：启用从服务（例如 macOS 上的“连续互通相机”）导入项目提供程序的功能。

- **exportsItemProviders(_:onExport:onEdit:)**：导出可供快捷指令、快速操作和服务使用的读写项目提供程序。


---
source: https://developer.apple.com/documentation/SwiftUI/View/exportsItemProviders(_:onExport:)
crawled: 2025-12-02T17:43:34Z
---

# exportsItemProviders(_:onExport:)

**Instance Method**

Exports a read-only item provider for consumption by shortcuts, quick actions, and services.

## Declaration

```swift
nonisolated func exportsItemProviders(_ contentTypes: [UTType], onExport: @escaping () -> [NSItemProvider]) -> some View

```

## Parameters

- **contentTypes**: The types of content that the view supports exporting. An empty array means the view does not currently support exporting.
- **onExport**: A closure that will be called on request of the items by the shortcut or service.

## Discussion

If the associated view supports selection, the exported item should reflect that selected subpart.

## Importing and exporting using item providers

- **importsItemProviders(_:onImport:)**: Enables importing item providers from services, such as Continuity Camera on macOS.
- **exportsItemProviders(_:onExport:onEdit:)**: Exports a read-write item provider for consumption by shortcuts, quick actions, and services.

