--- 来源：https://developer.apple.com/documentation/SwiftUI/View/actionSheet(item:content:)

抓取时间：2025-12-01T10:25:02Z

---

# actionSheet(item:content:)

**实例方法**

使用给定的 item 作为操作表内容的数据源，呈现一个操作表。

## 声明

```swift
nonisolated func actionSheet<T>(item: Binding<T?>, content: (T) -> ActionSheet) -> some View where T : Identifiable

```

## 参数

- **item**：操作表可选数据源的绑定。当 `item` 不为 `nil` 时，系统会将内容传递给修饰符的闭包。您可以使用此内容填充您创建的操作表的字段，系统会将该操作表显示给用户。如果 `item` 发生更改，系统将关闭当前显示的操作表，并使用相同的流程将其替换为新的操作表。

- **content**：返回您创建的 [ActionSheet](../ActionSheet.zh-Hans.md) 的闭包。

## 讨论

当您需要使用数据源中的内容填充操作表的字段时，请使用此方法。以下示例显示了一个自定义数据源 `FileDetails`，它提供数据来填充操作表：

```swift
struct FileDetails: Identifiable {
    var id: String { name }
    let name: String
    let fileType: UTType
}
struct ConfirmFileImport: View {
    @State private var sheetDetail: FileDetails?
    var body: some View {
        Button("Show Action Sheet") {
            sheetDetail = FileDetails(name: "MyImageFile.png",
                                      fileType: .png)
        }
        .actionSheet(item: $sheetDetail) { detail in
            ActionSheet(
                title: Text("File Import"),
                message: Text("""
                         Import \(detail.name)?
                         File Type: \(detail.fileType.description)
                         """),
                buttons: [
                    .destructive(Text("Import"),
                                 action: importFile),
                    .cancel()
                ])
        }
    }

    func importFile() {
        // Handle import action.
    }
}
```

## 视图显示修饰符

- **actionSheet(isPresented:content:)**：当给定条件为真时，显示操作表。

- **alert(isPresented:content:)**：向用户显示警报。

- **alert(item:content:)**：向用户显示警报。


---
source: https://developer.apple.com/documentation/SwiftUI/View/actionSheet(item:content:)
crawled: 2025-12-01T10:25:02Z
---

# actionSheet(item:content:)

**Instance Method**

Presents an action sheet using the given item as a data source for the sheet’s content.

## Declaration

```swift
nonisolated func actionSheet<T>(item: Binding<T?>, content: (T) -> ActionSheet) -> some View where T : Identifiable

```

## Parameters

- **item**: A binding to an optional source of truth for the action sheet. When `item` is non-`nil`, the system passes the contents to the modifier’s closure. You use this content to populate the fields of an action sheet that you create that the system displays to the user. If `item` changes, the system dismisses the currently displayed action sheet and replaces it with a new one using the same process.
- **content**: A closure returning the [ActionSheet](../ActionSheet.zh-Hans.md) you create.

## Discussion

Use this method when you need to populate the fields of an action sheet with content from a data source. The example below shows a custom data source, `FileDetails`, that provides data to populate the action sheet:

```swift
struct FileDetails: Identifiable {
    var id: String { name }
    let name: String
    let fileType: UTType
}
struct ConfirmFileImport: View {
    @State private var sheetDetail: FileDetails?
    var body: some View {
        Button("Show Action Sheet") {
            sheetDetail = FileDetails(name: "MyImageFile.png",
                                      fileType: .png)
        }
        .actionSheet(item: $sheetDetail) { detail in
            ActionSheet(
                title: Text("File Import"),
                message: Text("""
                         Import \(detail.name)?
                         File Type: \(detail.fileType.description)
                         """),
                buttons: [
                    .destructive(Text("Import"),
                                 action: importFile),
                    .cancel()
                ])
        }
    }

    func importFile() {
        // Handle import action.
    }
}
```



## View presentation modifiers

- **actionSheet(isPresented:content:)**: Presents an action sheet when a given condition is true.
- **alert(isPresented:content:)**: Presents an alert to the user.
- **alert(item:content:)**: Presents an alert to the user.

