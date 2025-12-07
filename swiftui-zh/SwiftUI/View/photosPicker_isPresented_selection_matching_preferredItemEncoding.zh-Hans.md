--- 来源：https://developer.apple.com/documentation/SwiftUI/View/photosPicker(isPresented:selection:matching:preferredItemEncoding:)

抓取时间：2025-12-02T17:45:27Z

---

# photosPicker(isPresented:selection:matching:preferredItemEncoding:)

**实例方法**

显示一个照片选择器，用于选择 `PhotosPickerItem`。

## 声明

```swift
nonisolated func photosPicker(isPresented: Binding<Bool>, selection: Binding<PhotosPickerItem?>, matching filter: PHPickerFilter? = nil, preferredItemEncoding: PhotosPickerItem.EncodingDisambiguationPolicy = .automatic) -> some View

```

## 参数

- **isPresented**：照片选择器是否显示的绑定。

- **selection**：照片选择器中显示和选中的项目。

- **filter**：可显示的项目类型。默认值为 `nil`。设置为 `nil` 表示可显示所有支持的类型。

- **preferredItemEncoding**：所选项目的编码消歧策略。默认值为 `.automatic`。设置为 `.automatic` 表示将使用系统确定的最佳编码。

## 讨论

用户仅明确授予对其选择的项目的访问权限，因此无需照片库访问授权。

## 选择照片

- **PhotosPicker**：显示照片选择器的视图，用于从照片库中选择素材。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，从指定的照片库中选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**：显示一个照片选择器，从指定的照片库中选择 `PhotosPickerItem` 的集合。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，从指定的照片库中选择 `PhotosPickerItem` 的集合。

- **photosPickerAccessoryVisibility(_:edges:)**：设置照片选择器的辅助元素可见性。辅助元素包括内容和边缘之间的任何元素，例如导航栏或侧边栏。

- **photosPickerDisabledCapabilities(_:)**：禁用照片选择器的某些功能。

- **photosPickerStyle(_:)**：设置照片选择器的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/photosPicker(isPresented:selection:matching:preferredItemEncoding:)
crawled: 2025-12-02T17:45:27Z
---

# photosPicker(isPresented:selection:matching:preferredItemEncoding:)

**Instance Method**

Presents a Photos picker that selects a `PhotosPickerItem`.

## Declaration

```swift
nonisolated func photosPicker(isPresented: Binding<Bool>, selection: Binding<PhotosPickerItem?>, matching filter: PHPickerFilter? = nil, preferredItemEncoding: PhotosPickerItem.EncodingDisambiguationPolicy = .automatic) -> some View

```

## Parameters

- **isPresented**: The binding to whether the Photos picker should be shown.
- **selection**: The item being shown and selected in the Photos picker.
- **filter**: Types of items that can be shown. Default is `nil`. Setting it to `nil` means all supported types can be shown.
- **preferredItemEncoding**: The encoding disambiguation policy of the selected item. Default is `.automatic`. Setting it to `.automatic` means the best encoding determined by the system will be used.

## Discussion

The user explicitly grants access only to items they choose, so photo library access authorization is not needed.

## Selecting photos

- **PhotosPicker**: A view that displays a Photos picker for choosing assets from the photo library.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a `PhotosPickerItem` from a given photo library.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem`.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem` from a given photo library.
- **photosPickerAccessoryVisibility(_:edges:)**: Sets the accessory visibility of the Photos picker. Accessories include anything between the content and the edge, like the navigation bar or the sidebar.
- **photosPickerDisabledCapabilities(_:)**: Disables capabilities of the Photos picker.
- **photosPickerStyle(_:)**: Sets the mode of the Photos picker.

