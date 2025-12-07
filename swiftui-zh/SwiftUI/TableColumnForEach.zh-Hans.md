--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnForEach
抓取时间：2025-12-02T17:39:56Z

---

# TableColumnForEach

**Structure**

一种根据底层已识别数据集合按需计算列的结构。

## 声明

```swift
struct TableColumnForEach<Data, ID, RowValue, Sort, Content> where Data : RandomAccessCollection, ID : Hashable, RowValue == Content.TableRowValue, Sort == Content.TableColumnSortComparator, Content : TableColumnContent
```

## 概述

使用 `TableColumnForEach` 基于某种数据类型的 [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] 创建列。集合的元素必须符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 规范，或者需要向 `TableColumnForEach` 初始化器提供一个 `id` 参数。

以下示例展示了 `AudioSampleTrack` 的接口，它包含一个由动态数量的 `AudioChannel` 组成的 `AudioSample` 集合。`Table` 用于显示每个样本的行。它有一个静态列用于存储样本的时间戳，并使用 `TableColumnForEach` 实例为音轨中的每个音频通道生成一列。

```swift
struct AudioChannel: Identifiable {
    let name: String
    let id: UUID
}

struct AudioSample: Identifiable {
    let id: UUID
    let timestamp: TimeInterval
    func level(channel: AudioChannel.ID) -> Double
}

@Observable
class AudioSampleTrack {
    let channels: [AudioChannel]
    var samples: some RandomAccessCollection<AudioSample> { get }
}

struct ContentView: View {
    var track: AudioSampleTrack

    var body: some View {
        Table(track.samples) {
            TableColumn("Timestamp (ms)") { sample in
                Text(sample.timestamp, format: .number.scale(1000))
                    .monospacedDigit()
            }
            TableColumnForEach(track.channels) { channel in
                TableColumn(channel.name) { sample in
                    Text(sample.level(channel: channel.id),
                         format: .number.precision(.fractionLength(2))
                    )
                    .monospacedDigit()
                }
                .width(ideal: 70)
                .alignment(.numeric)
            }
        }
    }
}
```

## 创建集合

- **init(_:content:)**：创建一个实例，该实例基于底层数据的标识，在更新过程中唯一标识并创建表列。

- **init(_:id:content:)**：创建一个实例，该实例基于指向底层数据标识符的键路径，在更新过程中唯一标识并创建表列。

## 访问集合内容

- **content**：一个使用底层数据按需创建内容的函数。

- **data**：SwiftUI 用于动态创建列的底层已识别数据集合。

## 创建列

- **TableColumn**：用于显示表格中每一行视图的列。

- **TableColumnContent**：用于表示表格中列的类型。

- **TableColumnAlignment**：描述表格列内容的对齐方式。

- **TableColumnBuilder**：一个结果构建器，用于从闭包创建表格列内容。

## 符合以下规范

- TableColumnContent


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnForEach
crawled: 2025-12-02T17:39:56Z
---

# TableColumnForEach

**Structure**

A structure that computes columns on demand from an underlying collection of identified data.

## Declaration

```swift
struct TableColumnForEach<Data, ID, RowValue, Sort, Content> where Data : RandomAccessCollection, ID : Hashable, RowValue == Content.TableRowValue, Sort == Content.TableColumnSortComparator, Content : TableColumnContent
```

## Overview

Use `TableColumnForEach` to create columns based on a [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] of some data type. Either the collection’s elements must conform to [doc://com.apple.documentation/documentation/Swift/Identifiable] or you need to provide an `id` parameter to the `TableColumnForEach` initializer.

The following example shows the interface for an `AudioSampleTrack`, which h as a collection of `AudioSample` across a dynamic number of `AudioChannel`s. The `Table` is created for displaying rows for each sample. It has one static column for the sample’s timestamp and uses a `TableColumnForEach` instance to produce a column for each of the audio channels in the track.

```swift
struct AudioChannel: Identifiable {
    let name: String
    let id: UUID
}

struct AudioSample: Identifiable {
    let id: UUID
    let timestamp: TimeInterval
    func level(channel: AudioChannel.ID) -> Double
}

@Observable
class AudioSampleTrack {
    let channels: [AudioChannel]
    var samples: some RandomAccessCollection<AudioSample> { get }
}

struct ContentView: View {
    var track: AudioSampleTrack

    var body: some View {
        Table(track.samples) {
            TableColumn("Timestamp (ms)") { sample in
                Text(sample.timestamp, format: .number.scale(1000))
                    .monospacedDigit()
            }
            TableColumnForEach(track.channels) { channel in
                TableColumn(channel.name) { sample in
                    Text(sample.level(channel: channel.id),
                         format: .number.precision(.fractionLength(2))
                    )
                    .monospacedDigit()
                }
                .width(ideal: 70)
                .alignment(.numeric)
            }
        }
    }
}
```

## Creating the collection

- **init(_:content:)**: Creates an instance that uniquely identifies and creates table columns across updates based on the identity of the underlying data.
- **init(_:id:content:)**: Creates an instance that uniquely identifies and creates table columns across updates based on the provided key path to the underlying data’s identifier.

## Accessing collection content

- **content**: A function to create content on demand using the underlying data.
- **data**: The collection of underlying identified data that SwiftUI uses to create columns dynamically.

## Creating columns

- **TableColumn**: A column that displays a view for each row in a table.
- **TableColumnContent**: A type used to represent columns within a table.
- **TableColumnAlignment**: Describes the alignment of the content of a table column.
- **TableColumnBuilder**: A result builder that creates table column content from closures.

## Conforms To

- TableColumnContent

