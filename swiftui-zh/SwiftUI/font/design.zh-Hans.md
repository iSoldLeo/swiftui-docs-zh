--- 来源：https://developer.apple.com/documentation/swiftui/font/design
抓取时间：2025-12-05T22:21:38Z

---

# Font.Design

**Enumeration**

用于字体的设计。

## 声明

```swift
enum Design
```

## 获取字体设计

- **Font.Design.default**

- **Font.Design.monospaced**

- **Font.Design.rounded**

- **Font.Design.serif**

## 获取系统字体

- **system(_:design:weight:)**：获取使用指定样式、设计和字重的系统字体。

- **system(size:weight:design:)**：指定要使用的系统字体，以及样式、字重和要应用于文本的任何设计参数。

- **Font.TextStyle**：用于字体的动态文本样式。

- **Font.Weight**：用于字体的字重。

## 符合以下规范

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/font/design
crawled: 2025-12-05T22:21:38Z
---

# Font.Design

**Enumeration**

A design to use for fonts.

## Declaration

```swift
enum Design
```

## Getting font designs

- **Font.Design.default**
- **Font.Design.monospaced**
- **Font.Design.rounded**
- **Font.Design.serif**

## Getting system fonts

- **system(_:design:weight:)**: Gets a system font that uses the specified style, design, and weight.
- **system(size:weight:design:)**: Specifies a system font to use, along with the style, weight, and any design parameters you want applied to the text.
- **Font.TextStyle**: A dynamic text style to use for fonts.
- **Font.Weight**: A weight to use for fonts.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

