---
来源： https://developer.apple.com/documentation/swiftui/image/alloweddynamicrange(_:)
抓取时间： 2025-12-04T03:35:44Z
---

# allowedDynamicRange(_:)

**实例方法**

返回按指定的允许动态范围配置的新图像。

## 声明

```swift
func allowedDynamicRange(_ range: Image.DynamicRange?) -> Image
```

## 参数

- **range**：请求的动态范围，或 nil 表示恢复默认的允许范围。

## 返回值

新图像。

## 讨论

假设图像具有 HDR（ITU-R 2100）色彩空间且输出设备支持 HDR，下面的示例将启用特定图像视图的 HDR 渲染：

```swift
Image("hdr-asset").allowedDynamicRange(.high)
```

## 指定动态范围

- **allowedDynamicRange**：视图允许的动态范围，或为零。
- **Image.DynamicRange**：视图允许的动态范围。


---
source: https://developer.apple.com/documentation/swiftui/image/alloweddynamicrange(_:)
crawled: 2025-12-04T03:35:44Z
---

# allowedDynamicRange(_:)

**Instance Method**

Returns a new image configured with the specified allowed dynamic range.

## Declaration

```swift
func allowedDynamicRange(_ range: Image.DynamicRange?) -> Image
```

## Parameters

- **range**: The requested dynamic range, or nil to restore the default allowed range.

## Return Value

A new image.

## Discussion

The following example enables HDR rendering for a specific image view, assuming that the image has an HDR (ITU-R 2100) color space and the output device supports it:

```swift
Image("hdr-asset").allowedDynamicRange(.high)
```

## Specifying dynamic range

- **allowedDynamicRange**: The allowed dynamic range for the view, or nil.
- **Image.DynamicRange**

