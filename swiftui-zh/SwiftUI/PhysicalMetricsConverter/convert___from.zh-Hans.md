--- 来源：https://developer.apple.com/documentation/SwiftUI/PhysicalMetricsConverter/convert(_:from:)

抓取时间：2025-12-03T06:33:55Z

---

# convert(_:from:)

**实例方法**

将指定单位的长度转换为适用于此转换器所关联环境的以磅为单位的长度。

## 声明

```swift
@MainActor @preconcurrency func convert(_ lengthValue: CGFloat, from unit: UnitLength) -> CGFloat
```

## 返回值

以磅为单位的值。此值仅可在与此转换器关联的场景中使用。

## 转换单位长度

- **convert(_:to:)**：将点的坐标转换为指定单位的物理长度测量值。


---
source: https://developer.apple.com/documentation/SwiftUI/PhysicalMetricsConverter/convert(_:from:)
crawled: 2025-12-03T06:33:55Z
---

# convert(_:from:)

**Instance Method**

Converts a length in the specified unit to a length in points suitable for use in the environment this converter is associated with.

## Declaration

```swift
@MainActor @preconcurrency func convert(_ lengthValue: CGFloat, from unit: UnitLength) -> CGFloat
```

## Return Value

A value in points. Use this value only in the scene this converter was associated with.

## Converting a unit length

- **convert(_:to:)**: Converts a point’s coordinates to physical length measurements in the specified unit.

