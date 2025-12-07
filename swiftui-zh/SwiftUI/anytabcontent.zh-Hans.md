---
来源： https://developer.apple.com/documentation/swiftui/anytabcontent
抓取时间： 2025-12-04T13:08:22Z
---

# AnyTabContent

**Structure**

键入已删除的选项卡内容。

## 声明

```swift
struct AnyTabContent<SelectionValue> where SelectionValue : Hashable
```

## Initializers

- **init(_:)**：创建一个类型迭代的实例 `tabContent`.

## 配置标签页

- **sectionActions(content:)**：为部分添加自定义操作。
- **TabPlacement**：标签页可以出现的位置。
- **TabContentBuilder**：结果生成器，用于为支持编程选择的选项卡视图构造选项卡。该创建器要求选项卡视图中的所有选项卡具有相同的选择类型。
- **TabContent**：为选项卡视图中的可编程选择选项卡提供内容的类型。

## 符合

- 标签内容


---
source: https://developer.apple.com/documentation/swiftui/anytabcontent
crawled: 2025-12-04T13:08:22Z
---

# AnyTabContent

**Structure**

Type erased tab content.

## Declaration

```swift
struct AnyTabContent<SelectionValue> where SelectionValue : Hashable
```

## Initializers

- **init(_:)**: Create an instance that type-erases `tabContent`.

## Configuring a tab

- **sectionActions(content:)**: Adds custom actions to a section.
- **TabPlacement**: A place that a tab can appear.
- **TabContentBuilder**: A result builder that constructs tabs for a tab view that supports programmatic selection. This builder requires that all tabs in the tab view have the same selection type.
- **TabContent**: A type that provides content for programmatically selectable tabs in a tab view.

## Conforms To

- TabContent

