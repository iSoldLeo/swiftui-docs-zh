--- 来源：https://developer.apple.com/documentation/swiftui/symboleffecttransition
抓取时间：2025-12-04T13:23:12Z

---

# SymbolEffectTransition

**Structure**

创建一个过渡效果，将“出现”、“消失”、“绘制”或“绘制”符号动画应用于插入或移除的视图层级结构中的符号图像。

## 声明

```swift
@MainActor @frozen @preconcurrency struct SymbolEffectTransition
```

## 概述

其他视图不受此过渡效果的影响。

## 创建过渡效果

- **init(effect:options:)**

## 管理符号效果

- **symbolEffect(_:options:isActive:)**：返回一个添加了符号效果的新视图。

- **symbolEffect(_:options:value:)**：返回一个添加了符号效果的新视图。

- **symbolEffectsRemoved(_:)**：返回一个新视图，该视图继承的符号图像效果可能被移除，也可能保持不变。

## 符合以下规范

- Transition


---
source: https://developer.apple.com/documentation/swiftui/symboleffecttransition
crawled: 2025-12-04T13:23:12Z
---

# SymbolEffectTransition

**Structure**

Creates a transition that applies the Appear, Disappear, DrawOn or DrawOff symbol animation to symbol images within the inserted or removed view hierarchy.

## Declaration

```swift
@MainActor @frozen @preconcurrency struct SymbolEffectTransition
```

## Overview

Other views are unaffected by this transition.

## Creating a transition

- **init(effect:options:)**

## Managing symbol effects

- **symbolEffect(_:options:isActive:)**: Returns a new view with a symbol effect added to it.
- **symbolEffect(_:options:value:)**: Returns a new view with a symbol effect added to it.
- **symbolEffectsRemoved(_:)**: Returns a new view with its inherited symbol image effects either removed or left unchanged.

## Conforms To

- Transition

