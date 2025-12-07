---
来源：https://developer.apple.com/documentation/SwiftUI/TouchBar/init(id:content:)
抓取时间： 2025-12-03T06:46:43Z
---

# init(id:content:)

**Initializer**

创建具有全局唯一标识符的可定制触摸栏视图容器。

### 声明

```swift
init(id: String, @ViewBuilder content: () -> Content)
```

## 参数

- **id**：该触摸条的全局唯一标识符。
- **content**：触摸条要显示的视图集合。

## 讨论

确保`content` 中的每个视图都有一个明确的带有自定义标识符的`touchBarItemPresence` 值。

## 创建触摸栏视图

- **init(content:)**：创建不可定制的触摸栏视图容器。


---
source: https://developer.apple.com/documentation/SwiftUI/TouchBar/init(id:content:)
crawled: 2025-12-03T06:46:43Z
---

# init(id:content:)

**Initializer**

Creates a customizable Touch Bar view container with a globally unique identifier.

## Declaration

```swift
init(id: String, @ViewBuilder content: () -> Content)
```

## Parameters

- **id**: A globally unique identifier for this Touch Bar.
- **content**: A collection of views to be displayed by the Touch Bar.

## Discussion

Be sure that each view in `content` has an explicit `touchBarItemPresence` value with customization identifier.

## Creating a Touch Bar view

- **init(content:)**: Creates a non-customizable Touch Bar view container.

