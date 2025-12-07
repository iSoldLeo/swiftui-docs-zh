--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileMover(isPresented:files:onCompletion:)

抓取时间：2025-11-30T21:15:54Z

---

# fileMover(isPresented:files:onCompletion:)

**实例方法**

提供一个系统接口，允许用户将一组现有文件移动到新位置。

## 声明

```swift
nonisolated func fileMover<C>(isPresented: Binding<Bool>, files: C, onCompletion: @escaping (Result<[URL], any Error>) -> Void) -> some View where C : Collection, C.Element == URL

```

## 参数

- **isPresented**：用于绑定是否显示此接口。

- **files**：要移动的文件集合，包含 `URL`。

- **onCompletion**：操作成功或失败时将调用的回调函数。要访问接收到的 URL，请调用 `startAccessingSecurityScopedResource`。不再需要访问时，请调用 `stopAccessingSecurityScopedResource`。

## 讨论

为了使界面显示，`isPresented` 必须为 `true`，且 `files` 不能为空。操作完成后，在调用 `onCompletion` 之前，`isPresented` 将被设置为 `false`。如果用户取消操作，`isPresented` 将被设置为 `false`，并且不会调用 `onCompletion`。

## 移动文件

- **fileMover(isPresented:file:onCompletion:)**：显示一个系统界面，允许用户将现有文件移动到新位置。

- **fileMover(isPresented:file:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户将现有文件移动到新位置。

- **fileMover(isPresented:files:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户将多个现有文件移动到新位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileMover(isPresented:files:onCompletion:)
crawled: 2025-11-30T21:15:54Z
---

# fileMover(isPresented:files:onCompletion:)

**Instance Method**

Presents a system interface for allowing the user to move a collection of existing files to a new location.

## Declaration

```swift
nonisolated func fileMover<C>(isPresented: Binding<Bool>, files: C, onCompletion: @escaping (Result<[URL], any Error>) -> Void) -> some View where C : Collection, C.Element == URL

```

## Parameters

- **isPresented**: A binding to whether the interface should be shown.
- **files**: A collection of `URL`s for the files to be moved.
- **onCompletion**: A callback that will be invoked when the operation has has succeeded or failed. To access the received URLs, call `startAccessingSecurityScopedResource`. When the access is no longer required, call `stopAccessingSecurityScopedResource`.

## Discussion



In order for the interface to appear, both `isPresented` must be `true` and `files` must not be empty. When the operation is finished, `isPresented` will be set to `false` before `onCompletion` is called. If the user cancels the operation, `isPresented` will be set to `false` and `onCompletion` will not be called.

## Moving a file

- **fileMover(isPresented:file:onCompletion:)**: Presents a system interface for allowing the user to move an existing file to a new location.
- **fileMover(isPresented:file:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to move an existing file to a new location.
- **fileMover(isPresented:files:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to move a collection of existing files to a new location.

