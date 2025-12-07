---
来源： https://developer.apple.com/documentation/SwiftUI/PreviewProvider/platform
抓取时间： 2025-12-03T07:07:13Z
---

# 平台

**类型属性**

运行提供程序的平台。

## 声明

```swift
@MainActor @preconcurrency static var platform: PreviewPlatform? { get }
```

## 讨论

Xcode 基于当前选择的目标推断预览的平台。如果您有一个多平台的目标，并希望为预览推荐一个特定的目标，请执行`platform` 计算属性以提供提示，并指定[PreviewPlatform](../PreviewPlatform.zh-Hans.md) 值之一：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
    }

    static var platform: PreviewPlatform? {
        PreviewPlatform.tvOS
    }
}
```

除非您有多平台目标，否则 Xcode 会忽略此值。


---
source: https://developer.apple.com/documentation/SwiftUI/PreviewProvider/platform
crawled: 2025-12-03T07:07:13Z
---

# platform

**Type Property**

The platform on which to run the provider.

## Declaration

```swift
@MainActor @preconcurrency static var platform: PreviewPlatform? { get }
```

## Discussion

Xcode infers the platform for a preview based on the currently selected target. If you have a multiplatform target and want to suggest a particular target for a preview, implement the `platform` computed property to provide a hint, and specify one of the [PreviewPlatform](../PreviewPlatform.zh-Hans.md) values:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
    }

    static var platform: PreviewPlatform? {
        PreviewPlatform.tvOS
    }
}
```

Xcode ignores this value unless you have a multiplatform target.

