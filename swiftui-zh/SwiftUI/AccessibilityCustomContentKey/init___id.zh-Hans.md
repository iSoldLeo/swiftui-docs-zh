---
来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityCustomContentKey/init(_:id:)
抓取时间：2025-12-03T06:49:42Z
---

# init(_:id:)

**Initializer**

使用指定的标签和标识符创建`AccessibilityCustomContentKey`。

### 声明

```swift
init(_ label: LocalizedStringResource, id: String)
```

## 参数

- **label**：向用户描述此附加信息条目内容的本地化文本。例如"方向"。
- **id**：用于向 SwiftUI 标识附加信息条目的字符串。添加一个条目将替换以前任何具有相同标识符的值。

## 创建键

- **init(_:)**：创建一个带有指定标签的`AccessibilityCustomContentKey`。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityCustomContentKey/init(_:id:)
crawled: 2025-12-03T06:49:42Z
---

# init(_:id:)

**Initializer**

Create an `AccessibilityCustomContentKey` with the specified label and identifier.

## Declaration

```swift
init(_ label: LocalizedStringResource, id: String)
```

## Parameters

- **label**: Localized text describing to the user what is contained in this additional information entry. For example: “orientation”.
- **id**: String used to identify the additional information entry to SwiftUI. Adding an entry will replace any previous value with the same identifier.

## Creating a key

- **init(_:)**: Create an `AccessibilityCustomContentKey` with the specified label.

