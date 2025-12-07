---
来源： https://developer.apple.com/documentation/SwiftUI/GroupSectionsOfContent
抓取时间： 2025-12-02T16:16:06Z
---

# GroupSectionsOfContent

**Structure**

将给定视图的各部分转化为结果内容视图。

## 声明

```swift
struct GroupSectionsOfContent<Sections, Content> where Sections : View, Content : View
```

## 概览

您不会直接使用此类型。SwiftUI 会代表您创建此类型。

## 将视图分组到容器中

- 创建自定义容器视图**：访问单个子视图以组成灵活的容器视图。
- **Group**：将内容类型（如视图、场景或命令）的多个实例集合为一个单元的类型。
- **GroupElementsOfContent**：将给定视图的子视图转换为结果内容视图。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/GroupSectionsOfContent
crawled: 2025-12-02T16:16:06Z
---

# GroupSectionsOfContent

**Structure**

Transforms the sections of a given view into a resulting content view.

## Declaration

```swift
struct GroupSectionsOfContent<Sections, Content> where Sections : View, Content : View
```

## Overview

You don’t use this type directly. Instead SwiftUI creates this type on your behalf.

## Grouping views into a container

- **Creating custom container views**: Access individual subviews to compose flexible container views.
- **Group**: A type that collects multiple instances of a content type — like views, scenes, or commands — into a single unit.
- **GroupElementsOfContent**: Transforms the subviews of a given view into a resulting content view.

## Conforms To

- View

