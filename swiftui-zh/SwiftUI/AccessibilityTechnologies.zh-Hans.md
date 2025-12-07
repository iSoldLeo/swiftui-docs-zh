---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityTechnologies
抓取时间： 2025-12-02T16:49:07Z
---

# 无障碍技术

**Structure**

系统可用的无障碍技术。

## 声明

```swift
struct AccessibilityTechnologies
```

## 获取技术类型

- **switchControl**：代表开关控制的值，允许使用控制器按钮、呼吸控制开关或类似硬件使用整个系统。
- **voiceOver**：代表 VoiceOver 屏幕阅读器的值，允许在看不到屏幕的情况下使用系统。

### 创建技术类型

- **init()**：创建一个新的辅助功能技术结构，其中包含一个空的辅助功能技术集。

## 支持类型

- **AccessibilityAttachmentModifier**：视图修改器，为视图添加无障碍属性

## 符合

- 等价
- 可通过数组字形表达
- 可发送
- 可发送元类型
- 集合代数


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityTechnologies
crawled: 2025-12-02T16:49:07Z
---

# AccessibilityTechnologies

**Structure**

Accessibility technologies available to the system.

## Declaration

```swift
struct AccessibilityTechnologies
```

## Getting technology types

- **switchControl**: The value that represents a Switch Control, allowing the use of the entire system using controller buttons, a breath-controlled switch or similar hardware.
- **voiceOver**: The value that represents the VoiceOver screen reader, allowing use of the system without seeing the screen visually.

## Creating a technology type

- **init()**: Creates a new accessibility technologies structure with an empy accessibility technology set.

## Supporting types

- **AccessibilityAttachmentModifier**: A view modifier that adds accessibility properties to the view

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- Sendable
- SendableMetatype
- SetAlgebra

