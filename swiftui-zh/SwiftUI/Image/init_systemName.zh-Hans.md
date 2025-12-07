---
来源：https://developer.apple.com/documentation/SwiftUI/Image/init(systemName:)
抓取时间： 2025-12-01T09:18:21Z
---

# init(systemName:)

**Initializer**

创建系统符号映像。

## 声明

```swift
init(systemName: String)
```

## 参数

- **systemName**：系统符号映像的名称。使用 SF Symbols 应用程序查找系统符号映像的名称。

## 讨论

该初始化程序使用系统提供的符号创建图像。使用 [https://developer.apple.com/design/resources/#sf-symbols] 查找符号及其对应名称。

要从应用程序的资产目录中创建自定义符号图像，请使用 [init(_:bundle:)](init___bundle.zh-Hans.md)。

## 创建系统符号映像

- **init(systemName:variableValue:)**：创建带有变量值的系统符号映像。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(systemName:)
crawled: 2025-12-01T09:18:21Z
---

# init(systemName:)

**Initializer**

Creates a system symbol image.

## Declaration

```swift
init(systemName: String)
```

## Parameters

- **systemName**: The name of the system symbol image. Use the SF Symbols app to look up the names of system symbol images.

## Discussion

This initializer creates an image using a system-provided symbol. Use [https://developer.apple.com/design/resources/#sf-symbols] to find symbols and their corresponding names.

To create a custom symbol image from your app’s asset catalog, use [init(_:bundle:)](init___bundle.zh-Hans.md) instead.

## Creating a system symbol image

- **init(systemName:variableValue:)**: Creates a system symbol image with a variable value.

