--- 来源：https://developer.apple.com/documentation/SwiftUI/DismissBehavior
抓取时间：2025-12-02T17:21:10Z

---

# DismissBehavior

**Structure**

程序化窗口关闭行为。

## 声明

```swift
struct DismissBehavior
```

## 概述

使用此类型的值来控制当前事务期间的窗口关闭。

例如，要关闭显示模态视图（否则会阻止关闭）的窗口，请使用 [destructive](DismissBehavior/destructive.zh-Hans.md) 行为：

```swift
struct DismissWindowButton: View {
    @Environment(\.dismissWindow) private var dismissWindow

    var body: some View {
        Button("Close Auxiliary Window") {
            withTransaction(\.dismissBehavior, .destructive) {
                dismissWindow(id: "auxiliary")
            }
        }
    }
}
```

## 获取行为

- **destructive**：破坏性关闭行为。

- **interactive**：交互式关闭行为。

## 关闭窗口

- **dismissWindow**：存储在视图环境中的窗口关闭操作。

- **DismissWindowAction**：关闭与特定场景关联的窗口的操作。

- **dismiss**：关闭当前演示的操作。

- **DismissAction**：关闭演示的操作。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/DismissBehavior
crawled: 2025-12-02T17:21:10Z
---

# DismissBehavior

**Structure**

Programmatic window dismissal behaviors.

## Declaration

```swift
struct DismissBehavior
```

## Overview

Use values of this type to control window dismissal during the current transaction.

For example, to dismiss windows showing a modal presentation that would otherwise prohibit dismissal, use the [destructive](DismissBehavior/destructive.zh-Hans.md) behavior:

```swift
struct DismissWindowButton: View {
    @Environment(\.dismissWindow) private var dismissWindow

    var body: some View {
        Button("Close Auxiliary Window") {
            withTransaction(\.dismissBehavior, .destructive) {
                dismissWindow(id: "auxiliary")
            }
        }
    }
}
```

## Getting behaviors

- **destructive**: The destructive dismiss behavior.
- **interactive**: The interactive dismiss behavior.

## Closing windows

- **dismissWindow**: A window dismissal action stored in a view’s environment.
- **DismissWindowAction**: An action that dismisses a window associated to a particular scene.
- **dismiss**: An action that dismisses the current presentation.
- **DismissAction**: An action that dismisses a presentation.

## Conforms To

- Sendable
- SendableMetatype

