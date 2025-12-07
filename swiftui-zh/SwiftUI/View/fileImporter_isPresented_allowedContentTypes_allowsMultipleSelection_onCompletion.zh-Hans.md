--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)

抓取时间：2025-11-30T21:15:50Z

---

# fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)

**实例方法**

提供一个系统接口，允许用户导入多个文件。

## 声明

```swift
nonisolated func fileImporter(isPresented: Binding<Bool>, allowedContentTypes: [UTType], allowsMultipleSelection: Bool, onCompletion: @escaping (Result<[URL], any Error>) -> Void) -> some View

```

## 参数

- **isPresented**：绑定是否显示此接口。

- **allowedContentTypes**：支持导入的内容类型列表。

- **allowsMultipleSelection**：导入器是否允许用户选择多个文件进行导入。

- **onCompletion**：操作成功或失败时将调用的回调函数。要访问接收到的 URL，请调用 `startAccessingSecurityScopedResource`。不再需要访问时，请调用 `stopAccessingSecurityScopedResource`。

## 讨论

为了显示界面，`isPresented` 必须为 `true`。操作完成后，在调用 `onCompletion` 之前，`isPresented` 将被设置为 `false`。如果用户取消操作，`isPresented` 将被设置为 `false`，并且 `onCompletion` 将不会被调用。

例如，一个允许用户选择多个 PDF 文件供应用程序稍后合并的按钮可能如下所示：

```swift
   struct PickPDFsButton: View {
       @State private var showFileImporter = false
       var handlePickedPDF: (URL) -> Void

       var body: some View {
           Button {
               showFileImporter = true
           } label: {
               Label("Choose PDFs to combine", systemImage: "doc.circle")
           }
           .fileImporter(
               isPresented: $showFileImporter,
               allowedContentTypes: [.pdf],
               allowsMultipleSelection: true
           ) { result in
               switch result {
               case .success(let files):
                   files.forEach { file in
                       // gain access to the directory
                       let gotAccess = file.startAccessingSecurityScopedResource()
                       if !gotAccess { return }
                       // access the directory URL
                       // (read templates in the directory, make a bookmark, etc.)
                       handlePickedPDF(file)
                       // release access
                       file.stopAccessingSecurityScopedResource()
                   }
               case .failure(let error):
                   // handle error
                   print(error)
               }
           }
       }
   }
```

## 从文件导入

- **fileImporter(isPresented:allowedContentTypes:onCompletion:)**：显示一个系统界面，允许用户导入现有文件。

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户导入多个文件。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)
crawled: 2025-11-30T21:15:50Z
---

# fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)

**Instance Method**

Presents a system interface for allowing the user to import multiple files.

## Declaration

```swift
nonisolated func fileImporter(isPresented: Binding<Bool>, allowedContentTypes: [UTType], allowsMultipleSelection: Bool, onCompletion: @escaping (Result<[URL], any Error>) -> Void) -> some View

```

## Parameters

- **isPresented**: A binding to whether the interface should be shown.
- **allowedContentTypes**: The list of supported content types which can be imported.
- **allowsMultipleSelection**: Whether the importer allows the user to select more than one file to import.
- **onCompletion**: A callback that will be invoked when the operation has succeeded or failed. To access the received URLs, call `startAccessingSecurityScopedResource`. When the access is no longer required, call `stopAccessingSecurityScopedResource`.

## Discussion

In order for the interface to appear, `isPresented` must be `true`. When the operation is finished, `isPresented` will be set to `false` before `onCompletion` is called. If the user cancels the operation, `isPresented` will be set to `false` and `onCompletion` will not be called.



For example, a button that allows the user to choose multiple PDF files for the application to combine them later, might look like this:

```swift
   struct PickPDFsButton: View {
       @State private var showFileImporter = false
       var handlePickedPDF: (URL) -> Void

       var body: some View {
           Button {
               showFileImporter = true
           } label: {
               Label("Choose PDFs to combine", systemImage: "doc.circle")
           }
           .fileImporter(
               isPresented: $showFileImporter,
               allowedContentTypes: [.pdf],
               allowsMultipleSelection: true
           ) { result in
               switch result {
               case .success(let files):
                   files.forEach { file in
                       // gain access to the directory
                       let gotAccess = file.startAccessingSecurityScopedResource()
                       if !gotAccess { return }
                       // access the directory URL
                       // (read templates in the directory, make a bookmark, etc.)
                       handlePickedPDF(file)
                       // release access
                       file.stopAccessingSecurityScopedResource()
                   }
               case .failure(let error):
                   // handle error
                   print(error)
               }
           }
       }
   }
```



## Importing from file

- **fileImporter(isPresented:allowedContentTypes:onCompletion:)**: Presents a system interface for allowing the user to import an existing file.
- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to import multiple files.

