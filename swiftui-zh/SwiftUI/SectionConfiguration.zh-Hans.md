---
来源： https://developer.apple.com/documentation/SwiftUI/SectionConfiguration
抓取时间： 2025-12-02T17:40:08Z
---

# SectionConfiguration

**Structure**

指定节的内容。

## 声明

```swift
struct SectionConfiguration
```

## 概览

`SectionConfiguration`包括章节内容、页眉和页脚。

一个 `SectionConfiguration` 既可以表示一个明确的部分，也可以表示未明确封装在部分中的同级视图组。

值得注意的是，`header`、`footer` 和`content` 属性都是`SectionConfiguration`，因为它们可以由多个子视图组成。这意味着在大多数情况下，子视图集合应被视为一个集合（或者被索引到，或者与`ForEach`一起使用），或者子视图集合应被包装在一个容器视图中，如布局或其他自定义容器：

```swift
PinboardSectionsLayout {
    ForEach(sections: content) { section in
        VStack {
            HStack { section.header }
            section.content
            HStack { section.footer }
        }
    }
}
```

在这里，我们要为`PinboardSectionsLayout` 创建一个视图，以便在内容中的每个部分放置一个视图。为此，我们将 `ForEach` 主体包围在另一个容器（`VStack` 布局）中，确保 section.content 的不同子视图被周围的布局视为一个视图。此外，用`HStack` 布局包围页眉和页脚可以避免垂直堆叠页眉和页脚的子视图，因为我们希望在视觉上将它们组合在一起。

### 结构

- **SectionConfiguration.Actions**：章节的类型化操作。
- **SectionConfiguration.ID**：节的唯一标识符。

### 实例属性

- **actions**：与节相关的自定义操作。
- **containerValues**：与给定部分相关联的容器值。
- **content**：节主体的内容。
- **footer**：章节页脚的内容。
- **header**：章节页眉的内容。
- **id**：代表小节的唯一标识符。

## 将视图组织成章节

- **Section**：容器视图，可用于在某些视图中添加层次结构。
- **SectionCollection**：表示视图部分的不透明集合。

## 符合

- 可识别


---
source: https://developer.apple.com/documentation/SwiftUI/SectionConfiguration
crawled: 2025-12-02T17:40:08Z
---

# SectionConfiguration

**Structure**

Specifies the contents of a section.

## Declaration

```swift
struct SectionConfiguration
```

## Overview

A `SectionConfiguration` includes the content of the section, as well as its header and footer.

A `SectionConfiguration` can represent either an explicit section, or groups of sibling views that are not explicitly wrapped in a section.

Notably, the `header`, `footer` and `content` properties of a `SectionConfiguration` are all `SubviewsCollection`s as they can be made up of multiple subviews. That means in most cases, the subviews collection should be treated as a collection (either indexed into, or used with a `ForEach`), or the subviews collection should be wrapped in a container view, like a layout, or other custom container:

```swift
PinboardSectionsLayout {
    ForEach(sections: content) { section in
        VStack {
            HStack { section.header }
            section.content
            HStack { section.footer }
        }
    }
}
```

Here, we want to create one view for `PinboardSectionsLayout` to place per section in content. To do that, we surround the `ForEach` body in another container, a `VStack` layout, ensuring the different subviews of section.content are treated as a single view by the surrounding layout. Additionally, surrounding the header and footer in an `HStack` layout avoids vertically stacking subviews of the header and footer which we want visually grouped together.

## Structures

- **SectionConfiguration.Actions**: The type-erased actions of a section.
- **SectionConfiguration.ID**: A unique identifier for a section.

## Instance Properties

- **actions**: Custom actions associated with a section.
- **containerValues**: The container values associated with the given section.
- **content**: The contents of the section body.
- **footer**: The contents of the section footer.
- **header**: The contents of the section header.
- **id**: A unique identifier representing the section.

## Organizing views into sections

- **Section**: A container view that you can use to add hierarchy within certain views.
- **SectionCollection**: An opaque collection representing the sections of view.

## Conforms To

- Identifiable

