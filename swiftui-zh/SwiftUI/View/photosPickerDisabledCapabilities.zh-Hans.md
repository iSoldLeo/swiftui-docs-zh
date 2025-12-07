--- 来源：https://developer.apple.com/documentation/SwiftUI/View/photosPickerDisabledCapabilities(_:)

抓取时间：2025-12-02T17:45:31Z

---

# photosPickerDisabledCapabilities(_:)

**实例方法**

禁用照片选择器的功能。

## 声明

```swift
nonisolated func photosPickerDisabledCapabilities(_ disabledCapabilities: PHPickerCapabilities) -> some View

```

## 参数

- **disabledCapabilities**：一个或多个可用功能。

## 返回值

一个已禁用指定功能的照片选择器。

## 选择照片

- **PhotosPicker**：一个显示照片选择器的视图，用于从照片库中选择素材。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**：显示一个照片选择器，用于选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，用于从指定的照片库中选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**：显示一个照片选择器，用于选择 `PhotosPickerItem` 的集合。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，用于从指定的照片库中选择 `PhotosPickerItem` 的集合。

- **photosPickerAccessoryVisibility(_:edges:)**：设置照片选择器的辅助元素可见性。辅助元素包括内容和边缘之间的任何元素，例如导航栏或侧边栏。

- **photosPickerStyle(_:)**：设置照片选择器的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/photosPickerDisabledCapabilities(_:)
crawled: 2025-12-02T17:45:31Z
---

# photosPickerDisabledCapabilities(_:)

**Instance Method**

Disables capabilities of the Photos picker.

## Declaration

```swift
nonisolated func photosPickerDisabledCapabilities(_ disabledCapabilities: PHPickerCapabilities) -> some View

```

## Parameters

- **disabledCapabilities**: One or more of the available capabilities.

## Return Value

A Photos picker with specified capabilities that are disabled.

## Selecting photos

- **PhotosPicker**: A view that displays a Photos picker for choosing assets from the photo library.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a `PhotosPickerItem`.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a `PhotosPickerItem` from a given photo library.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem`.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem` from a given photo library.
- **photosPickerAccessoryVisibility(_:edges:)**: Sets the accessory visibility of the Photos picker. Accessories include anything between the content and the edge, like the navigation bar or the sidebar.
- **photosPickerStyle(_:)**: Sets the mode of the Photos picker.

