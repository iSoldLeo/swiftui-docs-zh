---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityCustomContentKey
抓取时间： 2025-12-02T17:44:22Z
---

# AccessibilityCustomContentKey

**Structure**

用于指定与附加辅助功能信息条目相关的标识符和标签的密钥。

## 声明

```swift
struct AccessibilityCustomContentKey
```

## 概览

使用`AccessibilityCustomContentKey` 和将该值作为参数的相关修饰符，可简化清除或替换代码中多处操作的附加信息条目。

## 创建键

- **init(_:)**：创建一个带有指定标签的`AccessibilityCustomContentKey`。
- **init(_:id:)**：使用指定的标签和标识符创建`AccessibilityCustomContentKey`。

## 添加自定义描述

- **accessibilityCustomContent(_:_:importance:)**：为视图添加额外的可访问性信息。

## 符合

- 可复制
- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityCustomContentKey
crawled: 2025-12-02T17:44:22Z
---

# AccessibilityCustomContentKey

**Structure**

Key used to specify the identifier and label associated with an entry of additional accessibility information.

## Declaration

```swift
struct AccessibilityCustomContentKey
```

## Overview

Use `AccessibilityCustomContentKey` and the associated modifiers taking this value as a parameter in order to simplify clearing or replacing entries of additional information that are manipulated from multiple places in your code.

## Creating a key

- **init(_:)**: Create an `AccessibilityCustomContentKey` with the specified label.
- **init(_:id:)**: Create an `AccessibilityCustomContentKey` with the specified label and identifier.

## Adding custom descriptions

- **accessibilityCustomContent(_:_:importance:)**: Add additional accessibility information to the view.

## Conforms To

- Copyable
- Equatable

