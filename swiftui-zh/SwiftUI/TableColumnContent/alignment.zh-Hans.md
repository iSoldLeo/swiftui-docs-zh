--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnContent/alignment(_:)

抓取时间：2025-12-01T11:29:48Z

---

# alignment(_:)

**实例方法**

设置列的对齐方式，同时应用于列标题标签和该列的行视图内容。

## 声明

```swift
@MainActor @preconcurrency func alignment(_ alignment: TableColumnAlignment) -> some TableColumnContent<Self.TableRowValue, Self.TableColumnSortComparator>

```

## 参数

- **alignment**：应用于列的对齐方式。

## 配置内容

- **customizationID(_:)**：设置使用 `TableColumnCustomization` 持久化列状态时要与列关联的标识符。

- **defaultVisibility(_:)**：设置表格列的默认可见性。

- **disabledCustomizationBehavior(_:)**：设置表格列的禁用自定义行为。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnContent/alignment(_:)
crawled: 2025-12-01T11:29:48Z
---

# alignment(_:)

**Instance Method**

Sets the alignment of the column, applying to both its column header label and the row view content for that column.

## Declaration

```swift
@MainActor @preconcurrency func alignment(_ alignment: TableColumnAlignment) -> some TableColumnContent<Self.TableRowValue, Self.TableColumnSortComparator>

```

## Parameters

- **alignment**: The alignment to apply to the column.

## Configuring the content

- **customizationID(_:)**: Sets the identifier to be associated with a column when persisting its state with `TableColumnCustomization`.
- **defaultVisibility(_:)**: Sets the default visibility of a table column.
- **disabledCustomizationBehavior(_:)**: Sets the disabled customization behavior for a table column.

