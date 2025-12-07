--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileMover(isPresented:file:onCompletion:onCancellation:)

抓取时间：2025-11-30T21:15:54Z

---

# fileMover(isPresented:file:onCompletion:onCancellation:)

**实例方法**

显示一个系统对话框，允许用户将现有文件移动到新位置。

## 声明

```swift
nonisolated func fileMover(isPresented: Binding<Bool>, file: URL?, onCompletion: @escaping (Result<URL, any Error>) -> Void, onCancellation: @escaping () -> Void) -> some View

```

## 参数

- **isPresented**：用于绑定是否显示对话框。

- **file**：要移动的文件的 URL。

- **onCompletion**：操作成功或失败时将调用的回调函数。 `result` 指示操作是成功还是失败。要访问接收到的 URL，请调用 `startAccessingSecurityScopedResource`。不再需要访问时，请调用 `stopAccessingSecurityScopedResource`。

- **onCancellation**：用户取消操作时将调用的回调函数。

## 讨论

例如，允许用户移动文件的按钮可能如下所示：

```swift
  struct MoveFileButton: View {
      @State private var showFileMover = false
      var file: URL
      var onCompletion: (URL) -> Void
      var onCancellation: (() -> Void)?

      var body: some View {
          Button {
              showFileMover = true
          } label: {
              Label("Choose destination", systemImage: "folder.circle")
          }
          .fileMover(isPresented: $showFileMover, file: file) { result in
              switch result {
              case .success(let url):
                  guard url.startAccessingSecurityScopedResource() else {
                      return
                  }
                  onCompletion(url)
                  url.stopAccessingSecurityScopedResource()
              case .failure(let error):
                  print(error)
                  // handle error
              }
          } onCancellation: {
              onCancellation?()
          }
      }
  }
```

## 移动文件

- **fileMover(isPresented:file:onCompletion:)**：提供一个系统界面，允许用户将现有文件移动到新位置。

- **fileMover(isPresented:files:onCompletion:)**：提供一个系统界面，允许用户将一组现有文件移动到新位置。

- **fileMover(isPresented:files:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户将一组现有文件移动到新位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileMover(isPresented:file:onCompletion:onCancellation:)
crawled: 2025-11-30T21:15:54Z
---

# fileMover(isPresented:file:onCompletion:onCancellation:)

**Instance Method**

Presents a system dialog for allowing the user to move an existing file to a new location.

## Declaration

```swift
nonisolated func fileMover(isPresented: Binding<Bool>, file: URL?, onCompletion: @escaping (Result<URL, any Error>) -> Void, onCancellation: @escaping () -> Void) -> some View

```

## Parameters

- **isPresented**: A binding to whether the dialog should be shown.
- **file**: The URL of the file to be moved.
- **onCompletion**: A callback that will be invoked when the operation has succeeded or failed. The `result` indicates whether the operation succeeded or failed. To access the received URLs, call `startAccessingSecurityScopedResource`. When the access is no longer required, call `stopAccessingSecurityScopedResource`.
- **onCancellation**: A callback that will be invoked if the user cancels the operation.

## Discussion



For example, a button that allows the user to move a file might look like this:

```swift
  struct MoveFileButton: View {
      @State private var showFileMover = false
      var file: URL
      var onCompletion: (URL) -> Void
      var onCancellation: (() -> Void)?

      var body: some View {
          Button {
              showFileMover = true
          } label: {
              Label("Choose destination", systemImage: "folder.circle")
          }
          .fileMover(isPresented: $showFileMover, file: file) { result in
              switch result {
              case .success(let url):
                  guard url.startAccessingSecurityScopedResource() else {
                      return
                  }
                  onCompletion(url)
                  url.stopAccessingSecurityScopedResource()
              case .failure(let error):
                  print(error)
                  // handle error
              }
          } onCancellation: {
              onCancellation?()
          }
      }
  }
```

## Moving a file

- **fileMover(isPresented:file:onCompletion:)**: Presents a system interface for allowing the user to move an existing file to a new location.
- **fileMover(isPresented:files:onCompletion:)**: Presents a system interface for allowing the user to move a collection of existing files to a new location.
- **fileMover(isPresented:files:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to move a collection of existing files to a new location.

