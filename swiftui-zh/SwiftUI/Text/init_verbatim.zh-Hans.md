--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/init(verbatim:)

抓取时间：2025-12-02T21:48:16Z

---

# init(verbatim:)

**Initializer**

创建一个文本视图，用于显示不带本地化的字符串字面量。

## 声明

```swift
init(verbatim content: String)
```

## 参数

- **content**：要显示的字符串，不带本地化。

## 说明

使用此初始化器创建一个不带本地化的文本视图，用于显示字符串字面量：

```swift
Text(verbatim: "pencil") // Displays the string "pencil" in any locale.
```

如果要在显示字符串字面量之前对其进行本地化，请改用 [init(_:tableName:bundle:comment:)](init___tableName_bundle_comment.zh-Hans.md) 初始化器。如果要显示字符串变量，请使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-9d1g4] 初始化器，它还会绕过本地化。

## 创建文本视图

- **init(_:tableName:bundle:comment:)**：创建一个文本视图，显示由键标识的本地化内容。

- **init(_:)**：创建一个文本视图，显示带样式的属性内容。

- **init(_:style:)**：创建一个实例，使用特定样式显示本地化的日期和时间。

- **init(_:format:)**：创建一个文本视图，显示由相应格式样式支持的非字符串类型的格式化表示。

- **init(_:formatter:)**：创建一个文本视图，显示 Foundation 对象的格式化表示。

- **init(timerInterval:pauseTime:countsDown:showsHours:)**：创建一个实例，显示在指定时间间隔内计数的计时器。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/init(verbatim:)
crawled: 2025-12-02T21:48:16Z
---

# init(verbatim:)

**Initializer**

Creates a text view that displays a string literal without localization.

## Declaration

```swift
init(verbatim content: String)
```

## Parameters

- **content**: A string to display without localization.

## Discussion

Use this initializer to create a text view with a string literal without performing localization:

```swift
Text(verbatim: "pencil") // Displays the string "pencil" in any locale.
```

If you want to localize a string literal before displaying it, use the [init(_:tableName:bundle:comment:)](init___tableName_bundle_comment.zh-Hans.md) initializer instead. If you want to display a string variable, use the [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-9d1g4] initializer, which also bypasses localization.

## Creating a text view

- **init(_:tableName:bundle:comment:)**: Creates a text view that displays localized content identified by a key.
- **init(_:)**: Creates a text view that displays styled attributed content.
- **init(_:style:)**: Creates an instance that displays localized dates and times using a specific style.
- **init(_:format:)**: Creates a text view that displays the formatted representation of a nonstring type supported by a corresponding format style.
- **init(_:formatter:)**: Creates a text view that displays the formatted representation of a Foundation object.
- **init(timerInterval:pauseTime:countsDown:showsHours:)**: Creates an instance that displays a timer counting within the provided interval.

