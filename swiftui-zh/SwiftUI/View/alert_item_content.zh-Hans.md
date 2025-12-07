--- 来源：https://developer.apple.com/documentation/SwiftUI/View/alert(item:content:)

抓取时间：2025-12-03T05:35:56Z

---

# alert(item:content:)

**实例方法**

向用户显示一个警告框。

## 声明

```swift
nonisolated func alert<Item>(item: Binding<Item?>, content: (Item) -> Alert) -> some View where Item : Identifiable

```

## 参数

- **item**：指向警告框可选数据源的绑定。如果 `item` 不为 `nil`，系统会将内容传递给修饰符的闭包。您可以使用此内容填充您创建的、系统向用户显示的警告框的字段。如果 `item` 发生更改，系统将关闭当前显示的警报，并使用相同的流程将其替换为新的警报。

- **content**：返回警报的闭包。

## 讨论

当您需要显示包含来自您提供的可选数据源绑定信息的警报时，请使用此方法。以下示例显示了一个自定义数据源 `FileInfo`，其属性配置了警报的 `message` 字段：

```swift
struct FileInfo: Identifiable {
    var id: String { name }
    let name: String
    let fileType: UTType
}

struct ConfirmImportAlert: View {
    @State private var alertDetails: FileInfo?
    var body: some View {
        Button("Show Alert") {
            alertDetails = FileInfo(name: "MyImageFile.png",
                                    fileType: .png)
        }
        .alert(item: $alertDetails) { details in
            Alert(title: Text("Import Complete"),
                  message: Text("""
                    Imported \(details.name) \n File
                    type: \(details.fileType.description).
                    """),
                  dismissButton: .default(Text("Dismiss")))
        }
    }
}
```

## 视图显示修饰符

- **actionSheet(isPresented:content:)**：当给定条件为真时，显示操作表。

- **actionSheet(item:content:)**：使用给定项作为操作表内容的数据源来显示操作表。

- **alert(isPresented:content:)**：向用户显示警报。


---
source: https://developer.apple.com/documentation/SwiftUI/View/alert(item:content:)
crawled: 2025-12-03T05:35:56Z
---

# alert(item:content:)

**Instance Method**

Presents an alert to the user.

## Declaration

```swift
nonisolated func alert<Item>(item: Binding<Item?>, content: (Item) -> Alert) -> some View where Item : Identifiable

```

## Parameters

- **item**: A binding to an optional source of truth for the alert. if `item` is non-`nil`, the system passes the contents to the modifier’s closure. You use this content to populate the fields of an alert that you create that the system displays to the user. If `item` changes, the system dismisses the currently displayed alert and replaces it with a new one using the same process.
- **content**: A closure returning the alert to present.

## Discussion

Use this method when you need to show an alert that contains information from a binding to an optional data source that you provide. The example below shows a custom data source `FileInfo` whose properties configure the alert’s `message` field:

```swift
struct FileInfo: Identifiable {
    var id: String { name }
    let name: String
    let fileType: UTType
}

struct ConfirmImportAlert: View {
    @State private var alertDetails: FileInfo?
    var body: some View {
        Button("Show Alert") {
            alertDetails = FileInfo(name: "MyImageFile.png",
                                    fileType: .png)
        }
        .alert(item: $alertDetails) { details in
            Alert(title: Text("Import Complete"),
                  message: Text("""
                    Imported \(details.name) \n File
                    type: \(details.fileType.description).
                    """),
                  dismissButton: .default(Text("Dismiss")))
        }
    }
}
```



## View presentation modifiers

- **actionSheet(isPresented:content:)**: Presents an action sheet when a given condition is true.
- **actionSheet(item:content:)**: Presents an action sheet using the given item as a data source for the sheet’s content.
- **alert(isPresented:content:)**: Presents an alert to the user.

