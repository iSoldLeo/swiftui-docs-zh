---
来源： https://developer.apple.com/documentation/SwiftUI/SurfaceSnappingInfo/authorizationStatus-swift.type.property
抓取时间： 2025-12-03T05:32:55Z
---

# 授权状态

**类型属性**

表示用户是否授权提供更详细的场景表面信息的值。要请求这些详细的表面信息，请在`Info.plist` 文件中将`UIWantsDetailedSurfaceInfo` 设置为`YES`，并设置`NSWorldSensingUsageDescription` 以说明应用程序请求这些信息的原因。

## 声明

```swift
static var authorizationStatus: SurfaceSnappingInfo.AuthorizationStatus { get }
```


---
source: https://developer.apple.com/documentation/SwiftUI/SurfaceSnappingInfo/authorizationStatus-swift.type.property
crawled: 2025-12-03T05:32:55Z
---

# authorizationStatus

**Type Property**

A value that represents whether the user has authorized providing more detailed information about the surface scenes are snapped to. To request this detailed surface information, in your `Info.plist` file, set `UIWantsDetailedSurfaceInfo` to `YES` and set `NSWorldSensingUsageDescription` to provide a description of why your app is requesting this information.

## Declaration

```swift
static var authorizationStatus: SurfaceSnappingInfo.AuthorizationStatus { get }
```

