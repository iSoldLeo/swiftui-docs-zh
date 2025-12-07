--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnContent/defaultVisibility(_:)

抓取时间：2025-12-03T06:40:31Z

---

# defaultVisibility(_:)

**实例方法**

设置表格列的默认可见性。

## 声明

```swift
@MainActor @preconcurrency func defaultVisibility(_ visibility: Visibility) -> some TableColumnContent<Self.TableRowValue, Self.TableColumnSortComparator>

```

## 参数

- **visibility**：应用于列的默认可见性。

## 说明

`hidden` 列默认不可见，除非 `Table` 列也绑定到 `TableColumnCustomization` 列，并且该列的可见性已通过编程方式或用户方式修改。

## 配置内容

- **alignment(_:)**：设置列的对齐方式，同时应用于列标题标签和该列的行视图内容。

- **customizationID(_:)**：设置使用 `TableColumnCustomization` 持久化列状态时要关联的标识符。

- **disabledCustomizationBehavior(_:)**：设置表格列的禁用自定义行为。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnContent/defaultVisibility(_:)
crawled: 2025-12-03T06:40:31Z
---

# defaultVisibility(_:)

**Instance Method**

Sets the default visibility of a table column.

## Declaration

```swift
@MainActor @preconcurrency func defaultVisibility(_ visibility: Visibility) -> some TableColumnContent<Self.TableRowValue, Self.TableColumnSortComparator>

```

## Parameters

- **visibility**: The default visibility to apply to columns.

## Discussion

A `hidden` column will not be visible, unless the `Table` is also bound to `TableColumnCustomization` and either modified programmatically or by the user.

## Configuring the content

- **alignment(_:)**: Sets the alignment of the column, applying to both its column header label and the row view content for that column.
- **customizationID(_:)**: Sets the identifier to be associated with a column when persisting its state with `TableColumnCustomization`.
- **disabledCustomizationBehavior(_:)**: Sets the disabled customization behavior for a table column.

