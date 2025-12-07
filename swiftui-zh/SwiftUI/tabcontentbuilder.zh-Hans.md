---
来源： https://developer.apple.com/documentation/swiftui/tabcontentbuilder
抓取时间： 2025-12-04T13:08:20Z
---

# TabContentBuilder

**Structure**

一种结果生成器，用于为支持编程选择的选项卡视图构造选项卡。该创建器要求选项卡视图中的所有选项卡都具有相同的选择类型。

## 声明

```swift
@resultBuilder struct TabContentBuilder<TabValue> where TabValue : Hashable
```

## 结构

- **TabContentBuilder.Content**：基于构建器的选项卡视图内容的视图表示（带选择）。

## 类型方法

- **buildBlock(_:)**
- **buildBlock(_:_:)**
- **buildBlock(_:_:_:)**
- **buildBlock(_:_:_:_:)**
- **buildBlock(_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**
- **buildEither(first:)**
- **buildEither(second:)**
- **buildExpression(_:)**
- **buildIf(_:)**
- **buildLimitedAvailability(_:)**

## 配置选项卡

- **sectionActions(content:)**：为部分添加自定义操作。
- **TabPlacement**：标签页可以出现的位置。
- **TabContent**：为选项卡视图中可编程选择的选项卡提供内容的类型。
- **AnyTabContent**：擦除选项卡内容的类型。


---
source: https://developer.apple.com/documentation/swiftui/tabcontentbuilder
crawled: 2025-12-04T13:08:20Z
---

# TabContentBuilder

**Structure**

A result builder that constructs tabs for a tab view that supports programmatic selection. This builder requires that all tabs in the tab view have the same selection type.

## Declaration

```swift
@resultBuilder struct TabContentBuilder<TabValue> where TabValue : Hashable
```

## Structures

- **TabContentBuilder.Content**: A view representation of the content of a builder-based tab view with selection.

## Type Methods

- **buildBlock(_:)**
- **buildBlock(_:_:)**
- **buildBlock(_:_:_:)**
- **buildBlock(_:_:_:_:)**
- **buildBlock(_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**
- **buildEither(first:)**
- **buildEither(second:)**
- **buildExpression(_:)**
- **buildIf(_:)**
- **buildLimitedAvailability(_:)**

## Configuring a tab

- **sectionActions(content:)**: Adds custom actions to a section.
- **TabPlacement**: A place that a tab can appear.
- **TabContent**: A type that provides content for programmatically selectable tabs in a tab view.
- **AnyTabContent**: Type erased tab content.

