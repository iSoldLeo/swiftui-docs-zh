--- 来源：https://developer.apple.com/documentation/swiftui/keyframetrackcontentbuilder/conditional

抓取时间：2025-12-04T13:14:28Z

---

# KeyframeTrackContentBuilder.Conditional

**Structure**

来自结果构建器的条件结果。

＃＃ 宣言

```swift
struct Conditional<ConditionalValue, First, Second> where ConditionalValue == First.Value, First : KeyframeTrackContent, Second : KeyframeTrackContent, First.Value == Second.Value
```

## 构建关键帧轨道内容

- **buildArray(_:)**
- **buildBlock()**
- **buildEither(first:)**
- **buildEither(second:)**
- **buildExpression(_:)**
- **buildPartialBlock(accumulated:next:)**
- **buildPartialBlock(first:)**

## 符合

- 关键帧轨道内容


---
source: https://developer.apple.com/documentation/swiftui/keyframetrackcontentbuilder/conditional
crawled: 2025-12-04T13:14:28Z
---

# KeyframeTrackContentBuilder.Conditional

**Structure**

A conditional result from the result builder.

## Declaration

```swift
struct Conditional<ConditionalValue, First, Second> where ConditionalValue == First.Value, First : KeyframeTrackContent, Second : KeyframeTrackContent, First.Value == Second.Value
```

## Building keyframe track content

- **buildArray(_:)**
- **buildBlock()**
- **buildEither(first:)**
- **buildEither(second:)**
- **buildExpression(_:)**
- **buildPartialBlock(accumulated:next:)**
- **buildPartialBlock(first:)**

## Conforms To

- KeyframeTrackContent

