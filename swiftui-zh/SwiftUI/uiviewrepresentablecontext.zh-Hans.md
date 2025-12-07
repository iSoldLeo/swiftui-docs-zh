---
来源： https://developer.apple.com/documentation/swiftui/uiviewrepresentablecontext
抓取时间： 2025-12-04T11:33:43Z
---

# UIViewRepresentableContext

**Structure**

有关系统状态的上下文信息，用于创建和更新 UIKit 视图。

## 声明

```swift
@MainActor @preconcurrency struct UIViewRepresentableContext<Representable> where Representable : UIViewRepresentable
```

## 概览

[UIViewRepresentableContext](UIViewRepresentableContext.zh-Hans.md)结构包含有关系统当前状态的详细信息。在创建和更新视图时，系统会创建这些结构之一，并将其传递给自定义[UIViewRepresentable](UIViewRepresentable.zh-Hans.md) 实例的相应方法。使用此结构中的信息配置视图。例如，使用所提供的环境值配置视图的外观。请勿自行创建此结构。

## 协调与视图相关的交互

- **coordinator**：视图的相关协调器。
- **transaction**：当前事务。

## 获取当前环境数据

- **environment**：当前环境。

## 实例方法

- **animate(changes:completion:)**：使用当前事务中的动画对更改进行动画处理。

## 将 UIKit 视图添加到 SwiftUI 视图层次结构中

- **UIViewRepresentable**：UIKit 视图的封装器，用于将该视图集成到 SwiftUI 视图层次结构中。
- **UIViewControllerRepresentable**：表示 UIKit 视图控制器的视图。
- **UIViewControllerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 UIKit 视图控制器。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/uiviewrepresentablecontext
crawled: 2025-12-04T11:33:43Z
---

# UIViewRepresentableContext

**Structure**

Contextual information about the state of the system that you use to create and update your UIKit view.

## Declaration

```swift
@MainActor @preconcurrency struct UIViewRepresentableContext<Representable> where Representable : UIViewRepresentable
```

## Overview

A [UIViewRepresentableContext](UIViewRepresentableContext.zh-Hans.md) structure contains details about the current state of the system. When creating and updating your view, the system creates one of these structures and passes it to the appropriate method of your custom [UIViewRepresentable](UIViewRepresentable.zh-Hans.md) instance. Use the information in this structure to configure your view. For example, use the provided environment values to configure the appearance of your view. Don’t create this structure yourself.

## Coordinating view-related interactions

- **coordinator**: The view’s associated coordinator.
- **transaction**: The current transaction.

## Getting the current environment data

- **environment**: The current environment.

## Instance Methods

- **animate(changes:completion:)**: Animates changes using the animation in the current transaction.

## Adding UIKit views to SwiftUI view hierarchies

- **UIViewRepresentable**: A wrapper for a UIKit view that you use to integrate that view into your SwiftUI view hierarchy.
- **UIViewControllerRepresentable**: A view that represents a UIKit view controller.
- **UIViewControllerRepresentableContext**: Contextual information about the state of the system that you use to create and update your UIKit view controller.

## Conforms To

- Sendable
- SendableMetatype

