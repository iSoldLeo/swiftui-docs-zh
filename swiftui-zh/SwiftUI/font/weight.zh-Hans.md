--- 来源：https://developer.apple.com/documentation/swiftui/font/weight

抓取时间：2025-12-05T22:22:04Z

---

# Font.Weight

**Structure**

字体粗细设置。

## 声明

```swift
@frozen struct Weight
```

## 获取字体粗细

- **black**

- **bold**

- **heavy**

- **light**

- **medium**

- **regular**

- **semibold**

- **thin**

- **ultraLight**

## 获取系统字体

- **system(_:design:weight:)**：获取使用指定样式、设计和粗细的系统字体。

- **system(size:weight:design:)**：指定要使用的系统字体，以及样式、粗细和要应用于文本的任何设计参数。

- **Font.Design**：一种用于字体的设计。

- **Font.TextStyle**：一种用于字体的动态文本样式。

## 符合以下规范

- 位可复制 (BitwiseCopyable)

- 可复制 (Copyable)

- 可等值 (Equatable)

- 可哈希 (Hashable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/swiftui/font/weight
crawled: 2025-12-05T22:22:04Z
---

# Font.Weight

**Structure**

A weight to use for fonts.

## Declaration

```swift
@frozen struct Weight
```

## Getting font weights

- **black**
- **bold**
- **heavy**
- **light**
- **medium**
- **regular**
- **semibold**
- **thin**
- **ultraLight**

## Getting system fonts

- **system(_:design:weight:)**: Gets a system font that uses the specified style, design, and weight.
- **system(size:weight:design:)**: Specifies a system font to use, along with the style, weight, and any design parameters you want applied to the text.
- **Font.Design**: A design to use for fonts.
- **Font.TextStyle**: A dynamic text style to use for fonts.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

