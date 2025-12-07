---
来源： https://developer.apple.com/documentation/SwiftUI/TableRow/init(_:)
抓取时间： 2025-12-03T06:41:08Z
---

# init(_:)

**Initializer**

为给定值创建表行。

### 声明

```swift
init(_ value: Value)
```

## 参数

- **value**：行的值。

## 讨论

表格将某一行的值提供给表格的每一列，从而产生该列中每一行的单元格。

下面的示例为`Person` 类型的一个实例创建了一行。表格将此值传递给列，列中显示`Person` 的不同字段。

```swift
 TableRow(Person(givenName: "Tom", familyName: "Clark"))
```


---
source: https://developer.apple.com/documentation/SwiftUI/TableRow/init(_:)
crawled: 2025-12-03T06:41:08Z
---

# init(_:)

**Initializer**

Creates a table row for the given value.

## Declaration

```swift
init(_ value: Value)
```

## Parameters

- **value**: The value of the row.

## Discussion

The table provides the value of a row to each column of a table, which produces the cells for each row in the column.

The following example creates a row for one instance of the `Person` type. The table delivers this value to its columns, which displays different fields of `Person`.

```swift
 TableRow(Person(givenName: "Tom", familyName: "Clark"))
```

