--- 来源：https://developer.apple.com/documentation/SwiftUI/View/backgroundPreferenceValue(_:_:)

抓取时间：2025-11-30T21:17:37Z

---

# backgroundPreferenceValue(_:_:)

**实例方法**

从视图中读取指定的偏好设置值，并使用该值生成一个作为原始视图背景的第二视图。

## 声明

```swift
nonisolated func backgroundPreferenceValue<Key, T>(_ key: Key.Type = Key.self, @ViewBuilder _ transform: @escaping (Key.Value) -> T) -> some View where Key : PreferenceKey, T : View

```

## 参数

- **key**：要读取其值的偏好设置键类型。

- **transform**：一个根据从原始视图读取的偏好设置值生成背景视图的函数。

## 返回值

一个在原始视图下方叠加第二视图的视图。

## 根据偏好设置生成背景和叠加层

- **backgroundPreferenceValue(_:alignment:_:)**：从视图中读取指定的偏好设置值，并使用该值生成第二个视图，将其作为原始视图的背景。

- **overlayPreferenceValue(_:_:)**：从视图中读取指定的偏好设置值，并使用该值生成第二个视图，将其作为叠加层应用到原始视图上。

- **overlayPreferenceValue(_:alignment:_:)**：从视图中读取指定的偏好设置值，并使用该值生成第二个视图，将其作为叠加层应用到原始视图上。


---
source: https://developer.apple.com/documentation/SwiftUI/View/backgroundPreferenceValue(_:_:)
crawled: 2025-11-30T21:17:37Z
---

# backgroundPreferenceValue(_:_:)

**Instance Method**

Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.

## Declaration

```swift
nonisolated func backgroundPreferenceValue<Key, T>(_ key: Key.Type = Key.self, @ViewBuilder _ transform: @escaping (Key.Value) -> T) -> some View where Key : PreferenceKey, T : View

```

## Parameters

- **key**: The preference key type whose value is to be read.
- **transform**: A function that produces the background view from the preference value read from the original view.

## Return Value

A view that layers a second view behind the view.

## Generating backgrounds and overlays from preferences

- **backgroundPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **overlayPreferenceValue(_:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.
- **overlayPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.

