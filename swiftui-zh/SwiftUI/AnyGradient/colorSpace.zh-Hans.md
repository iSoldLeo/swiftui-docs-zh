--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyGradient/colorSpace(_:)

抓取时间：2025-12-01T11:14:46Z

---

# colorSpace(_:)

**实例方法**

返回一个使用指定颜色空间进行颜色插值的渐变版本。

## 声明

```swift
func colorSpace(_ space: Gradient.ColorSpace) -> AnyGradient
```

## 参数

- **space**：新渐变将用于插值其组成颜色的颜色空间。

## 返回值

一个使用指定颜色空间进行颜色插值的新渐变。

## 说明

```swift
Rectangle().fill(.linearGradient(
    colors: [.white, .blue]).colorSpace(.perceptual))
```


---
source: https://developer.apple.com/documentation/SwiftUI/AnyGradient/colorSpace(_:)
crawled: 2025-12-01T11:14:46Z
---

# colorSpace(_:)

**Instance Method**

Returns a version of the gradient that will use a specified color space for interpolating between its colors.

## Declaration

```swift
func colorSpace(_ space: Gradient.ColorSpace) -> AnyGradient
```

## Parameters

- **space**: The color space the new gradient will use to interpolate its constituent colors.

## Return Value

A new gradient that interpolates its colors in the specified color space.

## Discussion

```swift
Rectangle().fill(.linearGradient(
    colors: [.white, .blue]).colorSpace(.perceptual))
```

