--- 来源：https://developer.apple.com/documentation/SwiftUI/Commands/Body-swift.associatedtype

抓取时间：2025-12-03T06:22:26Z

---

# 主体

**关联类型**

表示此命令层级主体的命令类型。

## 声明

```swift
associatedtype Body : Commands
```

## 讨论

创建自定义命令时，Swift 会根据您对所需 [body-swift.property](body-swift_property.zh-Hans.md) 属性的实现来推断此类型。

## 命令实现

- **body**：命令层级的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Commands/Body-swift.associatedtype
crawled: 2025-12-03T06:22:26Z
---

# Body

**Associated Type**

The type of commands that represents the body of this command hierarchy.

## Declaration

```swift
associatedtype Body : Commands
```

## Discussion

When you create custom commands, Swift infers this type from your implementation of the required [body-swift.property](body-swift_property.zh-Hans.md) property.

## Implementing commands

- **body**: The contents of the command hierarchy.

