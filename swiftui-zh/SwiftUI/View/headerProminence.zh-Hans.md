--- 来源：https://developer.apple.com/documentation/SwiftUI/View/headerProminence(_:)

抓取时间：2025-12-02T17:39:33Z

---

# headerProminence(_:)

**实例方法**

设置此视图的标题突出显示程度。

## 声明

```swift
nonisolated func headerProminence(_ prominence: Prominence) -> some View

```

## 参数

- **prominence**：要应用的突出显示程度。

## 说明

在以下示例中，节标题以更高的突出显示程度显示：

```swift
List {
    Section(header: Text("Header")) {
        Text("Row")
    }
    .headerProminence(.increased)
}
.listStyle(.insetGrouped)
```

## 配置标题

- **headerProminence**：要应用于视图中节标题的突出显示程度。

- **Prominence**：指示视图层次结构突出显示程度的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/headerProminence(_:)
crawled: 2025-12-02T17:39:33Z
---

# headerProminence(_:)

**Instance Method**

Sets the header prominence for this view.

## Declaration

```swift
nonisolated func headerProminence(_ prominence: Prominence) -> some View

```

## Parameters

- **prominence**: The prominence to apply.

## Discussion

In the following example, the section header appears with increased prominence:

```swift
List {
    Section(header: Text("Header")) {
        Text("Row")
    }
    .headerProminence(.increased)
}
.listStyle(.insetGrouped)
```

## Configuring headers

- **headerProminence**: The prominence to apply to section headers within a view.
- **Prominence**: A type indicating the prominence of a view hierarchy.

