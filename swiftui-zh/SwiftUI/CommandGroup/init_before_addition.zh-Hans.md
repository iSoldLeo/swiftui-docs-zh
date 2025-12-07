---
来源：https://developer.apple.com/documentation/SwiftUI/CommandGroup/init(before:additional:)
抓取时间： 2025-12-01T11:11:34Z
---

# init(before:addition:)

**Initializer**

描述将给定视图添加到指定组开头的值。

## 声明

```swift
init(before group: CommandGroupPlacement, @ViewBuilder addition: () -> Content)
```

## 创建命令组

- **init(after:addition:)**：描述将给定视图添加到指定组末尾的值。
- **init(replacing:addition:)**：描述用给定视图完全替换指定组内容的值。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroup/init(before:addition:)
crawled: 2025-12-01T11:11:34Z
---

# init(before:addition:)

**Initializer**

A value describing the addition of the given views to the beginning of the indicated group.

## Declaration

```swift
init(before group: CommandGroupPlacement, @ViewBuilder addition: () -> Content)
```

## Creating a command group

- **init(after:addition:)**: A value describing the addition of the given views to the end of the indicated group.
- **init(replacing:addition:)**: A value describing the complete replacement of the contents of the indicated group with the given views.

