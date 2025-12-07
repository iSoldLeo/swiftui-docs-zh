--- 来源：https://developer.apple.com/documentation/SwiftUI/View/postToPhotosSharedAlbumSheet(isPresented:items:photoLibrary:defaultAlbumIdentifier:completion:)

抓取时间：2025-12-02T17:25:07Z

---

# postToPhotosSharedAlbumSheet(isPresented:items:photoLibrary:defaultAlbumIdentifier:completion:)

**实例方法**

显示一个“添加到共享相册”表单，允许用户将指定项目添加到共享相册。

## 声明

```swift
@MainActor func postToPhotosSharedAlbumSheet(isPresented: Binding<Bool>, items: [PHPickerResult], photoLibrary: PHPhotoLibrary, defaultAlbumIdentifier: String? = nil, completion: ((Result<Void, any Error>) -> Void)? = nil) -> some View

```

## 说明

- isPresented：绑定是否显示表单。

- items：要添加到共享相册的项目。

- photoLibrary：要从中选择的图库。

- defaultAlbumIdentifier：要预先选择的共享专辑的标识符。如果未提供，用户可以在用户界面中手动选择共享专辑。

- completion：请求完成后调用此函数并返回结果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/postToPhotosSharedAlbumSheet(isPresented:items:photoLibrary:defaultAlbumIdentifier:completion:)
crawled: 2025-12-02T17:25:07Z
---

# postToPhotosSharedAlbumSheet(isPresented:items:photoLibrary:defaultAlbumIdentifier:completion:)

**Instance Method**

Presents an “Add to Shared Album” sheet that allows the user to post the given items to a shared album.

## Declaration

```swift
@MainActor func postToPhotosSharedAlbumSheet(isPresented: Binding<Bool>, items: [PHPickerResult], photoLibrary: PHPhotoLibrary, defaultAlbumIdentifier: String? = nil, completion: ((Result<Void, any Error>) -> Void)? = nil) -> some View

```

## Discussion

- isPresented: The binding to whether the sheet should be shown.
- items: The items to be posted to the shared album.
- photoLibrary: Library to choose from.
- defaultAlbumIdentifier: Identifier for the shared album to be pre-selected. If none provided user can manually choose the shared album in UI.
- completion: Called with the result on completion of the request.

