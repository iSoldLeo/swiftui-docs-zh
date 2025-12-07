--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transformAnchorPreference(key:value:transform:)

抓取时间：2025-11-30T21:17:35Z

---

# transformAnchorPreference(key:value:transform:)

**实例方法**

为指定的偏好设置键设置一个值。该值是键的当前值和一个与当前坐标空间关联的几何值的函数，允许读取该值的用户将几何值转换为其本地坐标。

## 声明

```swift
nonisolated func transformAnchorPreference<A, K>(key _: K.Type = K.self, value: Anchor<A>.Source, transform: @escaping (inout K.Value, Anchor<A>) -> Void) -> some View where K : PreferenceKey

```

## 参数

- **key**：偏好设置键的类型。

- **value**：当前坐标空间中的几何值。

- **transform**：用于生成偏好设置值的函数。

## 返回值

返回一个用于写入首选项的新视图版本。

## 基于几何图形设置首选项

- **anchorPreference(key:value:transform:)**：为指定的首选项键设置一个值。该值是与当前坐标空间关联的几何图形值的函数，允许读取该值的用户将几何图形转换为其本地坐标。


---
source: https://developer.apple.com/documentation/SwiftUI/View/transformAnchorPreference(key:value:transform:)
crawled: 2025-11-30T21:17:35Z
---

# transformAnchorPreference(key:value:transform:)

**Instance Method**

Sets a value for the specified preference key, the value is a function of the key’s current value and a geometry value tied to the current coordinate space, allowing readers of the value to convert the geometry to their local coordinates.

## Declaration

```swift
nonisolated func transformAnchorPreference<A, K>(key _: K.Type = K.self, value: Anchor<A>.Source, transform: @escaping (inout K.Value, Anchor<A>) -> Void) -> some View where K : PreferenceKey

```

## Parameters

- **key**: The preference key type.
- **value**: The geometry value in the current coordinate space.
- **transform**: The function to produce the preference value.

## Return Value

A new version of the view that writes the preference.

## Setting preferences based on geometry

- **anchorPreference(key:value:transform:)**: Sets a value for the specified preference key, the value is a function of a geometry value tied to the current coordinate space, allowing readers of the value to convert the geometry to their local coordinates.

