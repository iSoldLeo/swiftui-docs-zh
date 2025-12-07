--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/primary
抓取时间：2025-12-03T06:25:13Z

---

# 主样式

**类型属性**

一种形状样式，映射到当前内容样式的第一级。

## 声明

```swift
static var primary: HierarchicalShapeStyle { get }
```

## 说明

此层级样式映射到当前前景样式的第一级；如果您未在视图环境中设置前景样式，则映射到默认前景样式的第一级。通常，您可以通过向 [foregroundStyle(_:)](../View/foregroundStyle.zh-Hans.md) 修饰符提供非层级样式来设置前景样式。

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 层级样式

- **secondary**：返回此形状样式的第二层级。

- **tertiary**：返回此形状样式的第三层级。

- **quaternary**：返回此形状样式的第四层级。

- **quinary**：返回此形状样式的第五层级。

- **secondary**：映射到当前内容样式第二层级的形状样式。

- **tertiary**：映射到当前内容样式第三层级的形状样式。

- **quaternary**：映射到当前内容样式第四层级的形状样式。

- **quinary**：映射到当前内容样式第五层级的形状样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/primary
crawled: 2025-12-03T06:25:13Z
---

# primary

**Type Property**

A shape style that maps to the first level of the current content style.

## Declaration

```swift
static var primary: HierarchicalShapeStyle { get }
```

## Discussion

This hierarchical style maps to the first level of the current foreground style, or to the first level of the default foreground style if you haven’t set a foreground style in the view’s environment. You typically set a foreground style by supplying a non-hierarchical style to the [foregroundStyle(_:)](../View/foregroundStyle.zh-Hans.md) modifier.

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Hierarchical styles

- **secondary**: Returns the second level of this shape style.
- **tertiary**: Returns the third level of this shape style.
- **quaternary**: Returns the fourth level of this shape style.
- **quinary**: Returns the fifth level of this shape style.
- **secondary**: A shape style that maps to the second level of the current content style.
- **tertiary**: A shape style that maps to the third level of the current content style.
- **quaternary**: A shape style that maps to the fourth level of the current content style.
- **quinary**: A shape style that maps to the fifth level of the current content style.

