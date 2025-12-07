---
来源： https://developer.apple.com/documentation/swiftui/immersivespacecontent
抓取时间： 2025-12-04T11:28:29Z
---

# 沉浸式空间内容

**Protocol**

可用作沉浸式空间内容的类型。

## 声明

```swift
@MainActor @preconcurrency protocol ImmersiveSpaceContent
```

## 概览

如果符合本协议的类型的基本声明中包含了本协议，那么该类型就继承了本协议的 `@preconcurrency @MainActor` 隔离性：

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

## 创建身临其境的空间内容

- **body**
- **Body**

## 支持类型

- **ImmersiveSpaceViewContent**：使用 SwiftUI 视图层次结构作为内容的沉浸式空间内容。

## 符合类型

- CompositorContentBuilder.Content
- 沉浸式空间视图内容


---
source: https://developer.apple.com/documentation/swiftui/immersivespacecontent
crawled: 2025-12-04T11:28:29Z
---

# ImmersiveSpaceContent

**Protocol**

A type that you can use as the content of an immersive space.

## Declaration

```swift
@MainActor @preconcurrency protocol ImmersiveSpaceContent
```

## Overview

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

## Creating immersive space content

- **body**
- **Body**

## Supporting types

- **ImmersiveSpaceViewContent**: Immersive space content that uses a SwiftUI view hierarchy as the content.

## Conforming Types

- CompositorContentBuilder.Content
- ImmersiveSpaceViewContent

