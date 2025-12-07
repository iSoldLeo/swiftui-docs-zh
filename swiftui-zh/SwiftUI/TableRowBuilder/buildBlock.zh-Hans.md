---
来源：https://developer.apple.com/documentation/SwiftUI/TableRowBuilder/buildBlock(_:_:_:_:_:_:_:_:_:_:_:_:_:_::)
抓取时间：2025-12-03T06:41:35Z


# buildBlock(_:_:_:_:_:_:_:_:_:)

**类型方法**

从九个来源中创建一个行结果。

## 声明

```swift
static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7, C8>(_ c0: C0, _ c1: C1, _ c2: C2, _ c3: C3, _ c4: C4, _ c5: C5, _ c6: C6, _ c7: C7, _ c8: C8) -> TupleTableRowContent<Value, (C0, C1, C2, C3, C4, C5, C6, C7, C8)> where Value == C0.TableRowValue, C0 : TableRowContent, C1 : TableRowContent, C2 : TableRowContent, C3 : TableRowContent, C4 : TableRowContent, C5 : TableRowContent, C6 : TableRowContent, C7 : TableRowContent, C8 : TableRowContent, C0.TableRowValue == C1.TableRowValue, C1.TableRowValue == C2.TableRowValue, C2.TableRowValue == C3.TableRowValue, C3.TableRowValue == C4.TableRowValue, C4.TableRowValue == C5.TableRowValue, C5.TableRowValue == C6.TableRowValue, C6.TableRowValue == C7.TableRowValue, C7.TableRowValue == C8.TableRowValue
```

## 从数据源建立一行

- **buildBlock(_:)**：创建单行结果。
- **buildBlock(_:_:)**：从两个来源创建行结果。
- **buildBlock(_:_:_:)**：从三个来源创建行结果。
- **buildBlock(_:_:_:_:)**：从四个来源创建行结果。
- **buildBlock(_:_:_:_:_:)**：从五个数据源创建行结果。
- **buildBlock(_:_:_:_:_:_:)**：从六个来源创建行结果。
- **buildBlock(_:_:_:_:_:_:_:)**：从七个数据源创建行结果。
- **buildBlock(_:_:_:_:_:_:_:_:)**：从 8 个数据源创建行结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**：从 10 个数据源创建行结果。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowBuilder/buildBlock(_:_:_:_:_:_:_:_:_:)
crawled: 2025-12-03T06:41:35Z
---

# buildBlock(_:_:_:_:_:_:_:_:_:)

**Type Method**

Creates a row result from nine sources.

## Declaration

```swift
static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7, C8>(_ c0: C0, _ c1: C1, _ c2: C2, _ c3: C3, _ c4: C4, _ c5: C5, _ c6: C6, _ c7: C7, _ c8: C8) -> TupleTableRowContent<Value, (C0, C1, C2, C3, C4, C5, C6, C7, C8)> where Value == C0.TableRowValue, C0 : TableRowContent, C1 : TableRowContent, C2 : TableRowContent, C3 : TableRowContent, C4 : TableRowContent, C5 : TableRowContent, C6 : TableRowContent, C7 : TableRowContent, C8 : TableRowContent, C0.TableRowValue == C1.TableRowValue, C1.TableRowValue == C2.TableRowValue, C2.TableRowValue == C3.TableRowValue, C3.TableRowValue == C4.TableRowValue, C4.TableRowValue == C5.TableRowValue, C5.TableRowValue == C6.TableRowValue, C6.TableRowValue == C7.TableRowValue, C7.TableRowValue == C8.TableRowValue
```

## Building a row from sources

- **buildBlock(_:)**: Creates a single row result.
- **buildBlock(_:_:)**: Creates a row result from two sources.
- **buildBlock(_:_:_:)**: Creates a row result from three sources.
- **buildBlock(_:_:_:_:)**: Creates a row result from four sources.
- **buildBlock(_:_:_:_:_:)**: Creates a row result from five sources.
- **buildBlock(_:_:_:_:_:_:)**: Creates a row result from six sources.
- **buildBlock(_:_:_:_:_:_:_:)**: Creates a row result from seven sources.
- **buildBlock(_:_:_:_:_:_:_:_:)**: Creates a row result from eight sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**: Creates a row result from ten sources.

