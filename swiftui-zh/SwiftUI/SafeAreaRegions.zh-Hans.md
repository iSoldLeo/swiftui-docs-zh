---
来源： https://developer.apple.com/documentation/SwiftUI/SafeAreaRegions
抓取时间： 2025-12-02T17:38:59Z
---

# 安全区域

**Structure**

一组符号化的安全区域。

## 声明

```swift
@frozen struct SafeAreaRegions
```

## 获取安全区域

- **all**：所有安全区域。
- **container**：由设备和用户界面内的容器定义的安全区域，包括顶部和底部栏等元素。
- **keyboard**：与视图内容上显示的任何软件键盘的当前范围相匹配的安全区域。

## 留在安全区域内

- **ignoresSafeArea(_:edges:)**：扩展视图的安全区域。
- **safeAreaInset(edge:alignment:spacing:content:)**：在修改的视图旁显示指定的内容。
- **safeAreaPadding(_:)**：将所提供的插页添加到此视图的安全区域。
- **safeAreaPadding(_:_:)**：将提供的嵌板添加到此视图的安全区域。

## 符合

- 比特可复制
- 可复制
- 等价
- 可表达数组原型
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/SafeAreaRegions
crawled: 2025-12-02T17:38:59Z
---

# SafeAreaRegions

**Structure**

A set of symbolic safe area regions.

## Declaration

```swift
@frozen struct SafeAreaRegions
```

## Getting safe area regions

- **all**: All safe area regions.
- **container**: The safe area defined by the device and containers within the user interface, including elements such as top and bottom bars.
- **keyboard**: The safe area matching the current extent of any software keyboard displayed over the view content.

## Staying in the safe areas

- **ignoresSafeArea(_:edges:)**: Expands the safe area of a view.
- **safeAreaInset(edge:alignment:spacing:content:)**: Shows the specified content beside the modified view.
- **safeAreaPadding(_:)**: Adds the provided insets into the safe area of this view.
- **safeAreaPadding(_:_:)**: Adds the provided insets into the safe area of this view.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

