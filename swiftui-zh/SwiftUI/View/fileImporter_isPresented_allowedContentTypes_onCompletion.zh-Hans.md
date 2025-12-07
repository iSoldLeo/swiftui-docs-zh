--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileImporter(isPresented:allowedContentTypes:onCompletion:)

抓取时间：2025-12-02T17:30:49Z

---

# fileImporter(isPresented:allowedContentTypes:onCompletion:)

**实例方法**

提供一个系统接口，允许用户导入现有文件。

## 声明

```swift
nonisolated func fileImporter(isPresented: Binding<Bool>, allowedContentTypes: [UTType], onCompletion: @escaping (Result<URL, any Error>) -> Void) -> some View

```

## 参数

- **isPresented**：接口是否显示的绑定。

- **allowedContentTypes**：可导入的内容类型列表。

- **onCompletion**：操作成功或失败时将调用的回调函数。要访问接收到的 URL，请调用 `startAccessingSecurityScopedResource`。不再需要访问时，请调用 `stopAccessingSecurityScopedResource`。

## 讨论

为了显示界面，`isPresented` 必须为 `true`。操作完成后，在调用 `onCompletion` 之前，`isPresented` 将被设置为 `false`。如果用户取消操作，`isPresented` 将被设置为 `false`，并且不会调用 `onCompletion`。

例如，应用程序可以有一个按钮，允许用户选择每次启动时加载文档模板的默认目录。这样的按钮可能如下所示：

```swift
 struct PickTemplatesDirectoryButton: View {
     @State private var showFileImporter = false
     var onTemplatesDirectoryPicked: (URL) -> Void

     var body: some View {
         Button {
             showFileImporter = true
         } label: {
             Label("Choose templates directory", systemImage: "folder.circle")
         }
         .fileImporter(
             isPresented: $showFileImporter,
             allowedContentTypes: [.directory]
         ) { result in
              switch result {
              case .success(let directory):
                  // gain access to the directory
                  let gotAccess = directory.startAccessingSecurityScopedResource()
                  if !gotAccess { return }
                  // access the directory URL
                  // (read templates in the directory, make a bookmark, etc.)
                  onTemplatesDirectoryPicked(directory)
                  // release access
                  directory.stopAccessingSecurityScopedResource()
              case .failure(let error):
                  // handle error
                  print(error)
              }
         }
     }
 }
```

## 从文件导入

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)**：显示一个系统界面，允许用户导入多个文件。

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户导入多个文件。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileImporter(isPresented:allowedContentTypes:onCompletion:)
crawled: 2025-12-02T17:30:49Z
---

# fileImporter(isPresented:allowedContentTypes:onCompletion:)

**Instance Method**

Presents a system interface for allowing the user to import an existing file.

## Declaration

```swift
nonisolated func fileImporter(isPresented: Binding<Bool>, allowedContentTypes: [UTType], onCompletion: @escaping (Result<URL, any Error>) -> Void) -> some View

```

## Parameters

- **isPresented**: A binding to whether the interface should be shown.
- **allowedContentTypes**: The list of supported content types which can be imported.
- **onCompletion**: A callback that will be invoked when the operation has succeeded or failed. To access the received URLs, call `startAccessingSecurityScopedResource`. When the access is no longer required, call `stopAccessingSecurityScopedResource`.

## Discussion

In order for the interface to appear, `isPresented` must be `true`. When the operation is finished, `isPresented` will be set to `false` before `onCompletion` is called. If the user cancels the operation, `isPresented` will be set to `false` and `onCompletion` will not be called.



For example, an application can have a button that allows the user to choose the default directory with document templates loaded on every launch. Such a button might look like this:

```swift
 struct PickTemplatesDirectoryButton: View {
     @State private var showFileImporter = false
     var onTemplatesDirectoryPicked: (URL) -> Void

     var body: some View {
         Button {
             showFileImporter = true
         } label: {
             Label("Choose templates directory", systemImage: "folder.circle")
         }
         .fileImporter(
             isPresented: $showFileImporter,
             allowedContentTypes: [.directory]
         ) { result in
              switch result {
              case .success(let directory):
                  // gain access to the directory
                  let gotAccess = directory.startAccessingSecurityScopedResource()
                  if !gotAccess { return }
                  // access the directory URL
                  // (read templates in the directory, make a bookmark, etc.)
                  onTemplatesDirectoryPicked(directory)
                  // release access
                  directory.stopAccessingSecurityScopedResource()
              case .failure(let error):
                  // handle error
                  print(error)
              }
         }
     }
 }
```



## Importing from file

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)**: Presents a system interface for allowing the user to import multiple files.
- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to import multiple files.

