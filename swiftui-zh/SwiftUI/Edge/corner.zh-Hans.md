---
来源： https://developer.apple.com/documentation/swiftui/edge/corner
抓取时间： 2025-12-05T22:21:31Z
---

# 边缘.角落

**Enumeration**

表示矩形一个角的枚举。

## 声明

```swift
enum Corner
```

## 结构

- **Edge.Corner.Set**：一组有效的角。
- **Edge.Corner.Style**：矩形的每个角的样式。角的半径可以是固定的，也可以与容器形状同心。要创建具有可配置边角样式的形状，请调用[ConcentricRectangle](../ConcentricRectangle.zh-Hans.md) 的初始化器之一并传入样式。

## 枚举案例

- **Edge.Corner.bottomLeading**
- **Edge.Corner.bottomTrailing**
- **Edge.Corner.topLeading**
- **Edge.Corner.topTrailing**

## 符合

- CaseIterable
- 可复制
- 自定义调试字符串可转换
- 等价
- 可散列
- 原始可表示
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/edge/corner
crawled: 2025-12-05T22:21:31Z
---

# Edge.Corner

**Enumeration**

An enumeration to indicate one corner of a rectangle.

## Declaration

```swift
enum Corner
```

## Structures

- **Edge.Corner.Set**: An efficient set of corners.
- **Edge.Corner.Style**: The per-corner style of a rectangular shape. A corner can be of fixed corner radius, or be concentric to the container shape. To create such a shape with configurable corner styles, call one of the initializers of [ConcentricRectangle](../ConcentricRectangle.zh-Hans.md) and pass in the style.

## Enumeration Cases

- **Edge.Corner.bottomLeading**
- **Edge.Corner.bottomTrailing**
- **Edge.Corner.topLeading**
- **Edge.Corner.topTrailing**

## Conforms To

- CaseIterable
- Copyable
- CustomDebugStringConvertible
- Equatable
- Hashable
- RawRepresentable
- Sendable
- SendableMetatype

