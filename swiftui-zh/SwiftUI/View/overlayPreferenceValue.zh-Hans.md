--- 来源：https://developer.apple.com/documentation/SwiftUI/View/overlayPreferenceValue(_:_:)

抓取时间：2025-12-02T17:32:33Z

---

# overlayPreferenceValue(_:_:)

**实例方法**

从视图中读取指定的偏好设置值，并使用该值生成一个叠加在原始视图上的第二个视图。

## 声明

```swift
nonisolated func overlayPreferenceValue<Key, T>(_ key: Key.Type = Key.self, @ViewBuilder _ transform: @escaping (Key.Value) -> T) -> some View where Key : PreferenceKey, T : View

```

## 参数

- **key**：要读取其值的偏好设置键类型。

- **transform**：一个根据从原始视图读取的偏好设置值生成叠加视图的函数。

## 返回值

一个在原始视图上方叠加第二个视图的视图。

## 根据偏好设置生成背景和叠加层

- **backgroundPreferenceValue(_:_:)**：从视图中读取指定的偏好设置值，并使用该值生成第二个视图，该视图将作为原始视图的背景。

- **backgroundPreferenceValue(_:alignment:_:)**：从视图中读取指定的偏好设置值，并使用该值生成第二个视图，该视图将作为原始视图的背景。

- **overlayPreferenceValue(_:alignment:_:)**：从视图中读取指定的偏好设置值，并使用该值生成第二个视图，该视图将作为叠加层应用到原始视图上。


---
source: https://developer.apple.com/documentation/SwiftUI/View/overlayPreferenceValue(_:_:)
crawled: 2025-12-02T17:32:33Z
---

# overlayPreferenceValue(_:_:)

**Instance Method**

Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.

## Declaration

```swift
nonisolated func overlayPreferenceValue<Key, T>(_ key: Key.Type = Key.self, @ViewBuilder _ transform: @escaping (Key.Value) -> T) -> some View where Key : PreferenceKey, T : View

```

## Parameters

- **key**: The preference key type whose value is to be read.
- **transform**: A function that produces the overlay view from the preference value read from the original view.

## Return Value

A view that layers a second view in front of the view.

## Generating backgrounds and overlays from preferences

- **backgroundPreferenceValue(_:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **backgroundPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **overlayPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.

