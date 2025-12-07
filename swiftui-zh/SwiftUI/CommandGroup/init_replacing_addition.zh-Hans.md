---
来源：https://developer.apple.com/documentation/SwiftUI/CommandGroup/init(替换：添加：)
抓取时间： 2025-12-03T06:22:29Z
---

# init(replacing:addition:)

**Initializer**

描述用给定视图完全替换指定组内容的值。

## 声明

```swift
init(replacing group: CommandGroupPlacement, @ViewBuilder addition: () -> Content)
```

## 创建命令组

- **init(after:addition:)**：描述将给定视图添加到指定组末尾的值。
- **init(before:addition:)**：描述将给定视图添加到指定组开始处的值。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroup/init(replacing:addition:)
crawled: 2025-12-03T06:22:29Z
---

# init(replacing:addition:)

**Initializer**

A value describing the complete replacement of the contents of the indicated group with the given views.

## Declaration

```swift
init(replacing group: CommandGroupPlacement, @ViewBuilder addition: () -> Content)
```

## Creating a command group

- **init(after:addition:)**: A value describing the addition of the given views to the end of the indicated group.
- **init(before:addition:)**: A value describing the addition of the given views to the beginning of the indicated group.

