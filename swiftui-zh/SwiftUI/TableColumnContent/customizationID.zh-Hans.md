--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnContent/customizationID(_:)

抓取时间：2025-12-03T06:40:30Z

---

# customizationID(_:)

**实例方法**

设置使用 `TableColumnCustomization` 持久化列状态时要关联的标识符。

## 声明

```swift
@MainActor @preconcurrency func customizationID(_ id: String) -> some TableColumnContent<Self.TableRowValue, Self.TableColumnSortComparator>

```

## 参数

- **id**：要与列关联的标识符。

## 说明

除了将整个表格绑定到 `TableColumnCustomization` 之外，还需要允许用户自定义特定的表格列。

该标识符需要保持稳定，包括应用版本更新，因为它用于持久化用户自定义设置。

## 配置内容

- **alignment(_:)**：设置列的对齐方式，该设置同时应用于列标题标签和该列的行视图内容。

- **defaultVisibility(_:)**：设置表格列的默认可见性。

- **disabledCustomizationBehavior(_:)**：设置表格列的禁用自定义行为。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnContent/customizationID(_:)
crawled: 2025-12-03T06:40:30Z
---

# customizationID(_:)

**Instance Method**

Sets the identifier to be associated with a column when persisting its state with `TableColumnCustomization`.

## Declaration

```swift
@MainActor @preconcurrency func customizationID(_ id: String) -> some TableColumnContent<Self.TableRowValue, Self.TableColumnSortComparator>

```

## Parameters

- **id**: The identifier to associate with a column.

## Discussion

This is required to allow user customization of a specific table column, in addition to the table as a whole being provided a binding to a `TableColumnCustomization`.

The identifier needs to be stable, including across app version updates, since it is used to persist the user customization.

## Configuring the content

- **alignment(_:)**: Sets the alignment of the column, applying to both its column header label and the row view content for that column.
- **defaultVisibility(_:)**: Sets the default visibility of a table column.
- **disabledCustomizationBehavior(_:)**: Sets the disabled customization behavior for a table column.

