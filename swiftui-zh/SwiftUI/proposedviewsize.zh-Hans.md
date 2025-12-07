---
来源： https://developer.apple.com/documentation/swiftui/proposedviewsize
抓取时间： 2025-12-04T13:08:32Z
---

# 建议的视图尺寸

**Structure**

关于视图大小的建议。

## 声明

```swift
@frozen struct ProposedViewSize
```

## 概览

在 SwiftUI 的布局过程中，视图会选择自己的尺寸，但它们是根据父视图的尺寸建议来选择尺寸的。当您使用 [Layout](Layout.zh-Hans.md) 协议创建自定义布局时，您的布局容器会使用 `ProposedViewSize` 实例参与此过程。布局协议的方法会接收一个建议的尺寸输入，您可以在安排视图和计算复合容器的尺寸时将其考虑在内。同样，布局在测量和放置子视图时，也会为每个子视图提出一个尺寸。

布局容器在测量其子视图时，通常会提出几种尺寸并查看响应。容器可以利用这些信息来决定如何在其子视图之间分配空间。布局可能会尝试以下特殊建议：

- [zero](ProposedViewSize/zero.zh-Hans.md)提议；视图以最小尺寸响应。
- [infinity](ProposedViewSize/infinity.zh-Hans.md)提议；视图以最大尺寸响应。
- [unspecified](ProposedViewSize/unspecified.zh-Hans.md)提议；视图以其理想尺寸作出响应。

布局也可以一次只尝试一个维度的特殊情况。例如，[HStack](HStack.zh-Hans.md) 可能会测量其子视图宽度的灵活性，而高度则使用固定值。

## 获取标准提案

- **zero**：两个维度都为 0 的尺寸提案。
- **infinity**：在两个维度中都包含无穷大的尺寸方案。
- **unspecified**：未指定两个维度的建议尺寸。

## 创建自定义尺寸方案

- **init(_:)**：从指定尺寸创建新的建议尺寸。
- **init(width:height:)**：使用指定的宽度和高度创建新的建议尺寸。

## 获取建议尺寸

- **height**：建议的垂直尺寸，以点为单位。
- **width**：建议的水平尺寸，以点为单位。

## 修改建议

- **replacingUnspecifiedDimensions(by:)**：创建一个新方案，用指定尺寸的相应尺寸替换此方案中未指定的尺寸。

## 配置自定义布局

- **LayoutProperties**：布局容器的特定布局属性。
- **ViewSpacing**：视图的几何间距首选项集合。

## 符合

- 比特可复制
- 可复制
- 等价
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/proposedviewsize
crawled: 2025-12-04T13:08:32Z
---

# ProposedViewSize

**Structure**

A proposal for the size of a view.

## Declaration

```swift
@frozen struct ProposedViewSize
```

## Overview

During layout in SwiftUI, views choose their own size, but they do that in response to a size proposal from their parent view. When you create a custom layout using the [Layout](Layout.zh-Hans.md) protocol, your layout container participates in this process using `ProposedViewSize` instances. The layout protocol’s methods take a proposed size input that you can take into account when arranging views and calculating the size of the composite container. Similarly, your layout proposes a size to each of its own subviews when it measures and places them.

Layout containers typically measure their subviews by proposing several sizes and looking at the responses. The container can use this information to decide how to allocate space among its subviews. A layout might try the following special proposals:

- The [zero](ProposedViewSize/zero.zh-Hans.md) proposal; the view responds with its minimum size.
- The [infinity](ProposedViewSize/infinity.zh-Hans.md) proposal; the view responds with its maximum size.
- The [unspecified](ProposedViewSize/unspecified.zh-Hans.md) proposal; the view responds with its ideal size.

A layout might also try special cases for one dimension at a time. For example, an [HStack](HStack.zh-Hans.md) might measure the flexibility of its subviews’ widths, while using a fixed value for the height.

## Getting standard proposals

- **zero**: A size proposal that contains zero in both dimensions.
- **infinity**: A size proposal that contains infinity in both dimensions.
- **unspecified**: The proposed size with both dimensions left unspecified.

## Creating a custom size proposal

- **init(_:)**: Creates a new proposed size from a specified size.
- **init(width:height:)**: Creates a new proposed size using the specified width and height.

## Getting the proposal’s dimensions

- **height**: The proposed vertical size measured in points.
- **width**: The proposed horizontal size measured in points.

## Modifying a proposal

- **replacingUnspecifiedDimensions(by:)**: Creates a new proposal that replaces unspecified dimensions in this proposal with the corresponding dimension of the specified size.

## Configuring a custom layout

- **LayoutProperties**: Layout-specific properties of a layout container.
- **ViewSpacing**: A collection of the geometric spacing preferences of a view.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

