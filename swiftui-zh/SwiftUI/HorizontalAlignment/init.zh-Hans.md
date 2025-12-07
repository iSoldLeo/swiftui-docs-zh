--- 来源：https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/init(_:)

抓取时间：2025-12-01T11:25:53Z

---

# init(_:)

**Initializer**

创建指定类型的自定义水平对齐方式。

## 声明

```swift
init(_ id: any AlignmentID.Type)
```

## 参数

- **id**：唯一标识水平对齐方式的标识符类型。

## 说明

使用此初始化器创建自定义水平对齐方式。定义一个 [AlignmentID](../AlignmentID.zh-Hans.md) 类型，然后使用该类型在 [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) 上创建一个新的静态属性：

```swift
private struct OneQuarterAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.width / 4
    }
}

extension HorizontalAlignment {
    static let oneQuarter = HorizontalAlignment(OneQuarterAlignment.self)
}
```

您创建的每个水平对齐方式实例都需要一个唯一的标识符。更多信息，请参阅 [AlignmentID](../AlignmentID.zh-Hans.md)。

## 创建自定义比对

- **combineExplicit(_:)**：合并此实例生成的一系列显式比对值。


---
source: https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/init(_:)
crawled: 2025-12-01T11:25:53Z
---

# init(_:)

**Initializer**

Creates a custom horizontal alignment of the specified type.

## Declaration

```swift
init(_ id: any AlignmentID.Type)
```

## Parameters

- **id**: The type of an identifier that uniquely identifies a horizontal alignment.

## Discussion

Use this initializer to create a custom horizontal alignment. Define an [AlignmentID](../AlignmentID.zh-Hans.md) type, and then use that type to create a new static property on [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md):

```swift
private struct OneQuarterAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.width / 4
    }
}

extension HorizontalAlignment {
    static let oneQuarter = HorizontalAlignment(OneQuarterAlignment.self)
}
```

Every horizontal alignment instance that you create needs a unique identifier. For more information, see [AlignmentID](../AlignmentID.zh-Hans.md).

## Creating a custom alignment

- **combineExplicit(_:)**: Merges a sequence of explicit alignment values produced by this instance.

