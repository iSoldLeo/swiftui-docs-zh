---
来源： https://developer.apple.com/documentation/SwiftUI/WritingToolsBehavior
抓取时间： 2025-12-02T17:35:40Z
---

# 写作工具行为

**Structure**

写作工具对文本和文本输入的编辑体验。

## 声明

```swift
struct WritingToolsBehavior
```

## 类型属性

- **automatic**：将根据上下文提供适当的编辑体验，其中可能包括禁用书写工具。
- **complete**：尽可能提供完整的联机编辑体验。
- **disabled**：禁用书写工具。
- **limited**：尽可能提供有限的叠加面板体验。

## 配置书写工具行为

- **writingToolsBehavior(_:)**：指定环境中文本和文本输入的书写工具行为。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WritingToolsBehavior
crawled: 2025-12-02T17:35:40Z
---

# WritingToolsBehavior

**Structure**

The Writing Tools editing experience for text and text input.

## Declaration

```swift
struct WritingToolsBehavior
```

## Type Properties

- **automatic**: An appropriate editing experience will be provided based on context, which may include disabling the writing tools.
- **complete**: The complete inline-editing experience is provided if possible.
- **disabled**: The writing tools are disabled.
- **limited**: The limited, overlay-panel experience is provided if possible.

## Configuring the Writing Tools behavior

- **writingToolsBehavior(_:)**: Specifies the Writing Tools behavior for text and text input in the environment.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

