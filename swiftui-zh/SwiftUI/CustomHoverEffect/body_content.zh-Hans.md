--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/body(content:)

抓取时间：2025-12-03T06:45:39Z

---

# body(content:)

**实例方法**

定义此效果产生的效果。

## 声明

```swift
func body(content: Self.Content) -> Self.Body
```

## 参数

- **content**：用于构建自定义效果的空效果。

## 返回值

自定义效果。

## 说明

实现此方法是为了描述要应用于视图的自定义效果。`content` 是一个空效果，用于构建您的效果，该效果稍后将应用于视图，或与其他 `CustomHoverEffect` 组合使用。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/body(content:)
crawled: 2025-12-03T06:45:39Z
---

# body(content:)

**Instance Method**

Defines the effect produced by this effect.

## Declaration

```swift
func body(content: Self.Content) -> Self.Body
```

## Parameters

- **content**: An empty effect you use to compose the custom effect.

## Return Value

A custom effect.

## Discussion

You implement this method to describe a custom effect to apply to a view. `content` is an empty effect you use to build your effect, which will later be applied to a View, or combined with other `CustomHoverEffect`s.

