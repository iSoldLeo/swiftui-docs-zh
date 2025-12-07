---
来源：https://developer.apple.com/documentation/SwiftUI/ForEach/init(章节：内容：)
抓取时间：2025-12-02T20:59:55Z
---

# init(sections:content:)

**Initializer**

创建一个实例，用于唯一标识视图，并根据给定视图的章节在更新中创建视图。

### 声明

```swift
init<V>(sections view: V, @ViewBuilder content: @escaping (SectionConfiguration) -> Content) where Data == ForEachSectionCollection<Content>, ID == SectionConfiguration.ID, Content : View, V : View
```

## 参数

- **view**：要提取部分的视图。
- **content**：从部分创建视图的视图生成器


---
source: https://developer.apple.com/documentation/SwiftUI/ForEach/init(sections:content:)
crawled: 2025-12-02T20:59:55Z
---

# init(sections:content:)

**Initializer**

Creates an instance that uniquely identifies and creates views across updates based on the sections of a given view.

## Declaration

```swift
init<V>(sections view: V, @ViewBuilder content: @escaping (SectionConfiguration) -> Content) where Data == ForEachSectionCollection<Content>, ID == SectionConfiguration.ID, Content : View, V : View
```

## Parameters

- **view**: The view to extract the sections of.
- **content**: The view builder that creates views from sections

