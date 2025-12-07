---
来源： https://developer.apple.com/documentation/SwiftUI/SurfaceSnappingInfo/AuthorizationStatus-swift.enum
抓取时间： 2025-12-03T05:32:56Z
---

# SurfaceSnappingInfo.AuthorizationStatus

**Enumeration**

一种类型，表示用户是否已授权提供有关场景捕捉到的表面的更详细信息。

### 声明

```swift
enum AuthorizationStatus
```

## 概览

要提供`ARKit/SurfaceClassification` 数据，用户必须允许应用程序访问其周围环境的信息。要请求这些数据，请将`UIWantsDetailedSurfaceInfo` 设置为 `YES`，并将`NSWorldSensingUsageDescription` 设置为说明应用程序请求这些信息的原因。这些值在应用程序的 `Info.plist` 文件中设置。

## 枚举案例

- **SurfaceSnappingInfo.AuthorizationStatus.authorized**：用户已授权共享其周围环境的信息。
- **SurfaceSnappingInfo.AuthorizationStatus.denied**：用户拒绝提供有关其周围环境的信息。
- **SurfaceSnappingInfo.AuthorizationStatus.notDetermined**：用户尚未授权或拒绝提供有关其周围环境的信息。在您的 `UIWantsDetailedSurfaceInfo`中将 `UIWantsDetailedSurfaceInfo`设置为 `YES`，以便在用户首次从您的应用程序抓拍场景时请求有关其周围环境的信息。
- **SurfaceSnappingInfo.AuthorizationStatus.restricted**：用户无法授权分享其周围环境的详细信息。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SurfaceSnappingInfo/AuthorizationStatus-swift.enum
crawled: 2025-12-03T05:32:56Z
---

# SurfaceSnappingInfo.AuthorizationStatus

**Enumeration**

A type representing whether the user has granted permissions to provide more detailed information about the surface a scene is snapped to.

## Declaration

```swift
enum AuthorizationStatus
```

## Overview

To provide `ARKit/SurfaceClassification` data, the user must allow the app to access information about their surroundings. To request this data, set `UIWantsDetailedSurfaceInfo` to `YES` and set `NSWorldSensingUsageDescription` to provide a description of why your app is requesting this information. These values are set in your app’s `Info.plist` file.

## Enumeration Cases

- **SurfaceSnappingInfo.AuthorizationStatus.authorized**: The user has authorized sharing information about their surroundings.
- **SurfaceSnappingInfo.AuthorizationStatus.denied**: The user denied providing access to information about their surroundings.
- **SurfaceSnappingInfo.AuthorizationStatus.notDetermined**: The user has not yet authorized or denied providing information about their surroundings. Set `UIWantsDetailedSurfaceInfo` to `YES` in your `Info.plist` to request information about the user’s surroundings when they first snap a scene from your app.
- **SurfaceSnappingInfo.AuthorizationStatus.restricted**: The user is unable to grant authorization to share detailed information about their surroundings.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

