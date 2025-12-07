---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/Section/id
抓取时间： 2025-12-03T10:01:24Z
---

# id

**实例属性**

部分中所有实体共享的指定关键路径的值。

## 声明

```swift
@MainActor @preconcurrency let id: SectionIdentifier
```

## 讨论

通过在初始化过程中设置 [SectionedFetchRequest](../../SectionedFetchRequest.zh-Hans.md) 实例的 `sectionIdentifier` 参数，或通过修改相应 [SectionedFetchResults](../../SectionedFetchResults.zh-Hans.md) 实例的 [sectionIdentifier](../sectionIdentifier.zh-Hans.md) 属性，指定实体共享此值的键路径。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/Section/id
crawled: 2025-12-03T10:01:24Z
---

# id

**Instance Property**

The value that all entities in the section share for a specified key path.

## Declaration

```swift
@MainActor @preconcurrency let id: SectionIdentifier
```

## Discussion

Specify the key path that the entities share this value with by setting the [SectionedFetchRequest](../../SectionedFetchRequest.zh-Hans.md) instance’s `sectionIdentifier` parameter during initialization, or by modifying the corresponding [SectionedFetchResults](../../SectionedFetchResults.zh-Hans.md) instance’s [sectionIdentifier](../sectionIdentifier.zh-Hans.md) property.

