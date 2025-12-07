--- 来源：https://developer.apple.com/documentation/SwiftUI/View/importsItemProviders(_:onImport:)

抓取时间：2025-11-30T21:28:33Z

---

# importsItemProviders(_:onImport:)

**实例方法**

启用从服务（例如 macOS 上的“连续互通相机”）导入项目提供程序。

## 声明

```swift
nonisolated func importsItemProviders(_ contentTypes: [UTType], onImport: @escaping ([NSItemProvider]) -> Bool) -> some View

```

## 参数

- **contentTypes**：视图支持导入的内容类型。空数组表示视图当前不支持导入。

- **onImport**：将使用导入的服务项目调用的闭包。返回 `false` 表示接收项目失败。

## 使用项目提供程序进行导入和导出

- **exportsItemProviders(_:onExport:)**：导出只读项目提供程序，供快捷指令、快速操作和服务使用。

- **exportsItemProviders(_:onExport:onEdit:)**：导出读写项目提供程序，供快捷指令、快速操作和服务使用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/importsItemProviders(_:onImport:)
crawled: 2025-11-30T21:28:33Z
---

# importsItemProviders(_:onImport:)

**Instance Method**

Enables importing item providers from services, such as Continuity Camera on macOS.

## Declaration

```swift
nonisolated func importsItemProviders(_ contentTypes: [UTType], onImport: @escaping ([NSItemProvider]) -> Bool) -> some View

```

## Parameters

- **contentTypes**: The types of content that the view supports importing. An empty array means the view does not currently support importing.
- **onImport**: A closure that will be called with the imported service item. Return `false` to indicate that there was a failure to receive the items.

## Importing and exporting using item providers

- **exportsItemProviders(_:onExport:)**: Exports a read-only item provider for consumption by shortcuts, quick actions, and services.
- **exportsItemProviders(_:onExport:onEdit:)**: Exports a read-write item provider for consumption by shortcuts, quick actions, and services.

