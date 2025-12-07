---
来源： https://developer.apple.com/documentation/swiftui/accessibilityrotorcontent
抓取时间： 2025-12-04T13:40:25Z
---

# 无障碍浏览内容

**Protocol**

无障碍转子中的内容。

## 声明

```swift
@MainActor @preconcurrency protocol AccessibilityRotorContent
```

## 概览

一般由 `ForEach` 和 `if` 以及 `AccessibilityRotorEntry` 等控制流结构体生成。

如果符合本协议的类型在其基本声明中包含`@preconcurrency @MainActor`隔离，则该类型继承`@preconcurrency @MainActor`隔离协议：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 支持类型

- **body**：此 `AccessibilityRotorContent` 的内部内容。
- **Body**：该`AccessibilityRotorContent`内部内容的类型。

## 创建转子

- **AccessibilityRotorContentBuilder**：用于生成转子条目内容的结果生成器。
- **AccessibilityRotorEntry**：一个结构体，代表无障碍旋转器中的一个条目。

## 符合类型

- 无障碍旋转项
- 每个
- 组


---
source: https://developer.apple.com/documentation/swiftui/accessibilityrotorcontent
crawled: 2025-12-04T13:40:25Z
---

# AccessibilityRotorContent

**Protocol**

Content within an accessibility rotor.

## Declaration

```swift
@MainActor @preconcurrency protocol AccessibilityRotorContent
```

## Overview

Generally generated from control flow constructs like `ForEach` and `if`, and `AccessibilityRotorEntry`.

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Supporting types

- **body**: The internal content of this `AccessibilityRotorContent`.
- **Body**: The type for the internal content of this `AccessibilityRotorContent`.

## Creating rotors

- **AccessibilityRotorContentBuilder**: Result builder you use to generate rotor entry content.
- **AccessibilityRotorEntry**: A struct representing an entry in an Accessibility Rotor.

## Conforming Types

- AccessibilityRotorEntry
- ForEach
- Group

