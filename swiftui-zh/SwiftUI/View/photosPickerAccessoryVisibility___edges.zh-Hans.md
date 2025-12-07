--- 来源：https://developer.apple.com/documentation/SwiftUI/View/photosPickerAccessoryVisibility(_:edges:)

抓取时间：2025-11-30T21:30:28Z

---

# photosPickerAccessoryVisibility(_:edges:)

**实例方法**

设置照片选择器的辅助元素可见性。辅助元素包括内容和边缘之间的任何元素，例如导航栏或侧边栏。

## 声明

```swift
nonisolated func photosPickerAccessoryVisibility(_ visibility: Visibility, edges: Edge.Set = .all) -> some View

```

## 参数

- **edges**：要应用的辅助元素可见性。

- **edges**：一个或多个可用的边缘。

## 返回值

一个应用了指定辅助元素可见性的照片选择器。

## 选择照片

- **PhotosPicker**：显示照片选择器，用于从照片库中选择素材。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**：显示照片选择器，用于选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**：显示照片选择器，用于从指定照片库中选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**：显示照片选择器，用于选择 `PhotosPickerItem` 的集合。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**：显示照片选择器，用于从指定照片库中选择 `PhotosPickerItem` 的集合。

- **photosPickerDisabledCapabilities(_:)**：禁用照片选择器的功能。

- **photosPickerStyle(_:)**：设置照片选择器的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/photosPickerAccessoryVisibility(_:edges:)
crawled: 2025-11-30T21:30:28Z
---

# photosPickerAccessoryVisibility(_:edges:)

**Instance Method**

Sets the accessory visibility of the Photos picker. Accessories include anything between the content and the edge, like the navigation bar or the sidebar.

## Declaration

```swift
nonisolated func photosPickerAccessoryVisibility(_ visibility: Visibility, edges: Edge.Set = .all) -> some View

```

## Parameters

- **edges**: The accessory visibility to apply.
- **edges**: One or more of the available edges.

## Return Value

A Photos picker with the specified accessory visibility.

## Selecting photos

- **PhotosPicker**: A view that displays a Photos picker for choosing assets from the photo library.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a `PhotosPickerItem`.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a `PhotosPickerItem` from a given photo library.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem`.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem` from a given photo library.
- **photosPickerDisabledCapabilities(_:)**: Disables capabilities of the Photos picker.
- **photosPickerStyle(_:)**: Sets the mode of the Photos picker.

