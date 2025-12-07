---
来源： https://developer.apple.com/documentation/SwiftUI/GroupElementsOfContent
抓取时间： 2025-12-02T16:16:05Z
---

# GroupElementsOfContent

**Structure**

将给定视图的子视图转换为结果内容视图。

## 声明

```swift
struct GroupElementsOfContent<Subviews, Content> where Subviews : View, Content : View
```

## 概览

您不会直接使用此类型。SwiftUI 会代表您创建此类型。

## 将视图分组到容器中

- 创建自定义容器视图**：访问单个子视图以组成灵活的容器视图。
- **Group**：将内容类型（如视图、场景或命令）的多个实例集合为一个单元的类型。
- **GroupSectionsOfContent**：将给定视图的各部分转化为结果内容视图。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/GroupElementsOfContent
crawled: 2025-12-02T16:16:05Z
---

# GroupElementsOfContent

**Structure**

Transforms the subviews of a given view into a resulting content view.

## Declaration

```swift
struct GroupElementsOfContent<Subviews, Content> where Subviews : View, Content : View
```

## Overview

You don’t use this type directly. Instead SwiftUI creates this type on your behalf.

## Grouping views into a container

- **Creating custom container views**: Access individual subviews to compose flexible container views.
- **Group**: A type that collects multiple instances of a content type — like views, scenes, or commands — into a single unit.
- **GroupSectionsOfContent**: Transforms the sections of a given view into a resulting content view.

## Conforms To

- View

