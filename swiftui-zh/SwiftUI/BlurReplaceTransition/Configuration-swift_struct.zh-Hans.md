---
来源： https://developer.apple.com/documentation/SwiftUI/BlurReplaceTransition/Configuration-swift.struct
抓取时间： 2025-12-04T13:16:23Z
---

# BlurReplaceTransition.Configuration

**Structure**

过渡效果的配置属性。

## 声明

```swift
struct Configuration
```

## 获取过渡配置

- **downUp**：请求转换的配置，在移除视图时缩小视图，在插入视图时放大视图。
- **upUp**：请求在删除和插入视图时都向上缩放视图的转换的配置。

## 创建过渡

- **init(configuration:)**：创建新的过渡。
- **configuration**：过渡配置。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/BlurReplaceTransition/Configuration-swift.struct
crawled: 2025-12-04T13:16:23Z
---

# BlurReplaceTransition.Configuration

**Structure**

Configuration properties for a transition.

## Declaration

```swift
struct Configuration
```

## Getting the transition configuration

- **downUp**: A configuration that requests a transition that scales the view down while removing it and up while inserting it.
- **upUp**: A configuration that requests a transition that scales the view up while both removing and inserting it.

## Creating the transition

- **init(configuration:)**: Creates a new transition.
- **configuration**: The transition configuration.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

