--- 来源：https://developer.apple.com/documentation/SwiftUI/View/photosPickerStyle(_:)

抓取时间：2025-12-02T17:45:32Z

---

# photosPickerStyle(_:)

**实例方法**

设置照片选择器的模式。

## 声明

```swift
nonisolated func photosPickerStyle(_ style: PhotosPickerStyle) -> some View

```

## 参数

- **mode**：可用模式之一。

## 返回值

使用指定模式的照片选择器。

## 选择照片

- **PhotosPicker**：显示用于从照片库中选择照片的照片选择器的视图。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**：显示用于选择 `PhotosPickerItem` 的照片选择器。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，用于从指定照片库中选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**：显示一个照片选择器，用于从指定照片库中选择 `PhotosPickerItem` 的集合。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，用于从指定照片库中选择 `PhotosPickerItem` 的集合。

- **photosPickerAccessoryVisibility(_:edges:)**：设置照片选择器的辅助元素可见性。辅助元素包括内容和边缘之间的任何元素，例如导航栏或侧边栏。

- **photosPickerDisabledCapabilities(_:)**：禁用照片选择器的功能。


---
source: https://developer.apple.com/documentation/SwiftUI/View/photosPickerStyle(_:)
crawled: 2025-12-02T17:45:32Z
---

# photosPickerStyle(_:)

**Instance Method**

Sets the mode of the Photos picker.

## Declaration

```swift
nonisolated func photosPickerStyle(_ style: PhotosPickerStyle) -> some View

```

## Parameters

- **mode**: One of the available modes.

## Return Value

A Photos picker that uses the specified mode.

## Selecting photos

- **PhotosPicker**: A view that displays a Photos picker for choosing assets from the photo library.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a `PhotosPickerItem`.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a `PhotosPickerItem` from a given photo library.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem`.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem` from a given photo library.
- **photosPickerAccessoryVisibility(_:edges:)**: Sets the accessory visibility of the Photos picker. Accessories include anything between the content and the edge, like the navigation bar or the sidebar.
- **photosPickerDisabledCapabilities(_:)**: Disables capabilities of the Photos picker.

