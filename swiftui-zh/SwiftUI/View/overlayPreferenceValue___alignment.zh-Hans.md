--- 来源：https://developer.apple.com/documentation/SwiftUI/View/overlayPreferenceValue(_:alignment:_:)

抓取时间：2025-12-02T17:32:34Z

---

# overlayPreferenceValue(_:alignment:_:)

**实例方法**

从视图中读取指定的偏好设置值，并使用该值生成一个叠加在原始视图上的第二个视图。

## 声明

```swift
nonisolated func overlayPreferenceValue<K, V>(_ key: K.Type, alignment: Alignment = .center, @ViewBuilder _ transform: @escaping (K.Value) -> V) -> some View where K : PreferenceKey, V : View

```

## 参数

- **key**：要读取其值的偏好设置键类型。

- **alignment**：用于定位叠加视图相对于原始视图的可选对齐方式。

- **transform**：一个根据从原始视图读取的偏好设置值生成叠加视图的函数。

## 返回值

一个将第二个视图叠加在当前视图之前的视图。

## 说明

两个视图的首选项键值将被合并，并使其对父视图可见。

## 根据首选项生成背景和叠加层

- **backgroundPreferenceValue(_:_:)**：从视图中读取指定的首选项值，并使用该值生成一个作为原始视图背景的第二个视图。

- **backgroundPreferenceValue(_:alignment:_:)**：从视图中读取指定的首选项值，并使用该值生成一个作为原始视图背景的第二个视图。

- **overlayPreferenceValue(_:_:)**：从视图中读取指定的首选项值，并使用该值生成一个作为原始视图叠加层的第二个视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/overlayPreferenceValue(_:alignment:_:)
crawled: 2025-12-02T17:32:34Z
---

# overlayPreferenceValue(_:alignment:_:)

**Instance Method**

Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.

## Declaration

```swift
nonisolated func overlayPreferenceValue<K, V>(_ key: K.Type, alignment: Alignment = .center, @ViewBuilder _ transform: @escaping (K.Value) -> V) -> some View where K : PreferenceKey, V : View

```

## Parameters

- **key**: The preference key type whose value is to be read.
- **alignment**: An optional alignment to use when positioning the overlay view relative to the original view.
- **transform**: A function that produces the overlay view from the preference value read from the original view.

## Return Value

A view that layers a second view in front of the view.

## Discussion

The values of the preference key from both views are combined and made visible to the parent view.

## Generating backgrounds and overlays from preferences

- **backgroundPreferenceValue(_:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **backgroundPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **overlayPreferenceValue(_:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.

