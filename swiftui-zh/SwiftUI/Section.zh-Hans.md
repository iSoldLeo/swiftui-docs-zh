--- 来源：https://developer.apple.com/documentation/SwiftUI/Section

抓取时间：2025-12-02T16:23:38Z

---

# Section

**Structure**

一个容器视图，可用于在某些视图中添加层级结构。

## 声明

```swift
struct Section<Parent, Content, Footer>
```

## 概述

在诸如 [List](List.zh-Hans.md)、[Picker](Picker.zh-Hans.md) 和 [Form](Form.zh-Hans.md) 之类的视图中使用 `Section` 实例，可以将内容组织成不同的部分。每个部分都包含您可以为每个实例提供的自定义内容。您还可以为每个部分提供页眉和页脚。

### 可折叠部分

使用接受 `isExpanded` 绑定的初始化器，即可创建可展开和折叠的部分。在 [List](List.zh-Hans.md) 中使用 [sidebar](ListStyle/sidebar.zh-Hans.md) 样式的可折叠部分，会在部分标题旁边显示一个展开指示器。点击展开指示器即可切换部分内容的显示状态。

## 创建部分

- **init(content:)**：使用提供的部分内容创建一个部分。

- **init(_:content:)**：使用提供的部分内容创建一个部分。

## 添加页眉和页脚

- **init(content:header:)**：使用提供的部分内容创建一个包含页眉的部分。

- **init(content:footer:)**：使用提供的部分内容创建一个包含页脚的部分。

- **init(content:header:footer:)**：创建一个包含页眉、页脚和指定内容的节。

## 控制折叠功能

- **init(_:isExpanded:content:)**：创建一个包含指定内容的节。

- **init(isExpanded:content:header:)**：创建一个包含页眉、指定内容以及表示节展开状态的绑定的节。

## 已弃用符号

- **init(header:content:)**：创建一个包含页眉和指定内容的节。

- **init(footer:content:)**：创建一个包含页脚和指定内容的节。

- **init(header:footer:content:)**：创建一个包含页眉、页脚和指定内容的节。

- **collapsible(_:)**：设置用户是否可以折叠节。

## 将视图组织成节

- **SectionCollection**：表示视图节的不透明集合。

- **SectionConfiguration**：指定节的内容。

## 符合以下标准

- Copyable

- TableRowContent

- View


---
source: https://developer.apple.com/documentation/SwiftUI/Section
crawled: 2025-12-02T16:23:38Z
---

# Section

**Structure**

A container view that you can use to add hierarchy within certain views.

## Declaration

```swift
struct Section<Parent, Content, Footer>
```

## Overview

Use `Section` instances in views like [List](List.zh-Hans.md), [Picker](Picker.zh-Hans.md), and [Form](Form.zh-Hans.md) to organize content into separate sections. Each section has custom content that you provide on a per-instance basis. You can also provide headers and footers for each section.

### Collapsible sections

Create sections that expand and collapse by using an initializer that accepts an `isExpanded` binding. A collapsible section in a [List](List.zh-Hans.md) that uses the [sidebar](ListStyle/sidebar.zh-Hans.md) style shows a disclosure indicator next to the section’s header. Tapping on the disclosure indicator toggles the appearance of the section’s content.



## Creating a section

- **init(content:)**: Creates a section with the provided section content.
- **init(_:content:)**: Creates a section with the provided section content.

## Adding headers and footers

- **init(content:header:)**: Creates a section with a header and the provided section content.
- **init(content:footer:)**: Creates a section with a footer and the provided section content.
- **init(content:header:footer:)**: Creates a section with a header, footer, and the provided section content.

## Controlling collapsibility

- **init(_:isExpanded:content:)**: Creates a section with the provided section content.
- **init(isExpanded:content:header:)**: Creates a section with a header, the provided section content, and a binding representing the section’s expansion state.

## Deprecated symbols

- **init(header:content:)**: Creates a section with a header and the provided section content.
- **init(footer:content:)**: Creates a section with a footer and the provided section content.
- **init(header:footer:content:)**: Creates a section with a header, footer, and the provided section content.
- **collapsible(_:)**: Sets whether a section can be collapsed by the user.

## Organizing views into sections

- **SectionCollection**: An opaque collection representing the sections of view.
- **SectionConfiguration**: Specifies the contents of a section.

## Conforms To

- Copyable
- TableRowContent
- View

