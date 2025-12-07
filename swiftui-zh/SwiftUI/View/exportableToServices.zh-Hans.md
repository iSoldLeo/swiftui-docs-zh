--- 来源：https://developer.apple.com/documentation/SwiftUI/View/exportableToServices(_:)

抓取时间：2025-11-30T21:28:31Z

---

# exportableToServices(_:)

**实例方法**

导出可供快捷指令、快速操作和服务使用的项目。

## 声明

```swift
nonisolated func exportableToServices<T>(_ payload: @autoclosure @escaping () -> [T]) -> some View where T : Transferable

```

## 参数

- **payload**：当快捷指令或服务请求项目时，将调用此闭包。

## 说明

如果关联的视图支持选择，则导出的项目应反映所选的子部分。

```swift
var title: String
var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .exportableToServices([title])
}
```

## 导入和导出可传输项目

- **importableFromServices(for:action:)**：启用从服务（例如 macOS 上的“连续互通相机”）导入项目。

- **exportableToServices(_:onEdit:)**：导出可供快捷指令、快速操作和服务使用的读写项目。


---
source: https://developer.apple.com/documentation/SwiftUI/View/exportableToServices(_:)
crawled: 2025-11-30T21:28:31Z
---

# exportableToServices(_:)

**Instance Method**

Exports items for consumption by shortcuts, quick actions, and services.

## Declaration

```swift
nonisolated func exportableToServices<T>(_ payload: @autoclosure @escaping () -> [T]) -> some View where T : Transferable

```

## Parameters

- **payload**: A closure that will be called on request of the items by the shortcut or service.

## Discussion

If the associated view supports selection, the exported item should reflect that selected subpart.

```swift
var title: String
var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .exportableToServices([title])
}
```

## Importing and exporting transferable items

- **importableFromServices(for:action:)**: Enables importing items from services, such as Continuity Camera on macOS.
- **exportableToServices(_:onEdit:)**: Exports read-write items for consumption by shortcuts, quick actions, and services.

