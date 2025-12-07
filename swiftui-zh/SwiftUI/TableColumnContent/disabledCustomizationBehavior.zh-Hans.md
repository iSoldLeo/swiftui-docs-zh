--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnContent/disabledCustomizationBehavior(_:)

抓取时间：2025-12-03T06:40:31Z

---

# disabledCustomizationBehavior(_:)

**实例方法**

设置表格列的禁用自定义行为。

## 声明

```swift
@MainActor @preconcurrency func disabledCustomizationBehavior(_ behavior: TableColumnCustomizationBehavior) -> some TableColumnContent<Self.TableRowValue, Self.TableColumnSortComparator>

```

## 参数

- **behavior**：要禁用的行为，或 `.all`：不允许任何自定义。

## 说明

当包含列 `Table` 绑定到某个列 `TableColumnCustomization` 时，默认情况下，macOS 用户将可以自定义所有列（例如 `TableColumnCustomizationBehavior.all`）。此修饰符允许禁用特定行为。

此修饰符在 iOS 上无效，因为 `Table` 不支持任何内置的用户自定义功能。

这不会阻止通过编程方式更改表格列的自定义设置。

## 配置内容

- **alignment(_:)**：设置列的对齐方式，同时应用于列标题标签和该列的行视图内容。

- **customizationID(_:)**：设置使用 `TableColumnCustomization` 持久化列状态时要与列关联的标识符。

- **defaultVisibility(_:)**：设置表格列的默认可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnContent/disabledCustomizationBehavior(_:)
crawled: 2025-12-03T06:40:31Z
---

# disabledCustomizationBehavior(_:)

**Instance Method**

Sets the disabled customization behavior for a table column.

## Declaration

```swift
@MainActor @preconcurrency func disabledCustomizationBehavior(_ behavior: TableColumnCustomizationBehavior) -> some TableColumnContent<Self.TableRowValue, Self.TableColumnSortComparator>

```

## Parameters

- **behavior**: The behavior to disable, or `.all` to not allow any customization.

## Discussion

When the containing `Table` is bound to some `TableColumnCustomization`, all columns will be able to be customized by the user on macOS by default (i.e. `TableColumnCustomizationBehavior.all`). This modifier allows disabling specific behavior.

This modifier has no effect on iOS since `Table` does not support any built-in user customization features.

This does not prevent programmatic changes to a table column customization.

## Configuring the content

- **alignment(_:)**: Sets the alignment of the column, applying to both its column header label and the row view content for that column.
- **customizationID(_:)**: Sets the identifier to be associated with a column when persisting its state with `TableColumnCustomization`.
- **defaultVisibility(_:)**: Sets the default visibility of a table column.

