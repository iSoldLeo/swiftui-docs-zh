---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/surfaceSnappingInfo
抓取时间： 2025-12-03T06:08:18Z
---

# surfaceSnappingInfo

**实例属性**

提供有关场景当前抓取状态的信息。

## 声明

```swift
var surfaceSnappingInfo: SurfaceSnappingInfo { get }
```

## 讨论

使用环境中提供的 [SurfaceSnappingInfo](../SurfaceSnappingInfo.zh-Hans.md) 来修改视图内容

```swift
struct LightFixtureView: View {
    @Environment(\.surfaceSnappingInfo)
    var snappingInfo: SurfaceSnappingInfo

    var body: some View {
        if snappingInfo.isSnapped {
            switch SurfaceSnappingInfo.authorizationStatus {
                case .authorized:
                    switch snappingInfo.classification {
                        case .table:
                            LampView()
                        case .floor:
                            FloorLampView()
                        default:
                            DefaultLampView()
                    }
                default:
                    DefaultLampView()
            }
        } else {
            FloatingOrbLampView()
        }
    }
}
```

此环境值应在应用程序的视图中访问，而不是在应用程序或场景级别访问。如果您尝试在场景或应用程序级别访问该值，它将始终返回默认值。

如果您想访问场景捕捉到的表面分类，用户必须允许应用程序访问其周围环境的信息。在您的应用程序的`Info.plist`中，您应该将`UIWantsDetailedSurfaceInfo`设置为`YES`，并设置`NSWorldSensingUsageDescription`以提供您的应用程序请求此信息的原因描述。当用户第一次从您的应用程序抓拍场景时，该描述将显示给用户。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/surfaceSnappingInfo
crawled: 2025-12-03T06:08:18Z
---

# surfaceSnappingInfo

**Instance Property**

Provides information about the current snap state of the scene.

## Declaration

```swift
var surfaceSnappingInfo: SurfaceSnappingInfo { get }
```

## Discussion

Use the provided [SurfaceSnappingInfo](../SurfaceSnappingInfo.zh-Hans.md) from the environment to modify the content of your view

```swift
struct LightFixtureView: View {
    @Environment(\.surfaceSnappingInfo)
    var snappingInfo: SurfaceSnappingInfo

    var body: some View {
        if snappingInfo.isSnapped {
            switch SurfaceSnappingInfo.authorizationStatus {
                case .authorized:
                    switch snappingInfo.classification {
                        case .table:
                            LampView()
                        case .floor:
                            FloorLampView()
                        default:
                            DefaultLampView()
                    }
                default:
                    DefaultLampView()
            }
        } else {
            FloatingOrbLampView()
        }
    }
}
```

This environment value should be accessed inside a view of your app, not at the app or scene level. If you try to access this value at the scene or app level it will always return the default value.

If you would like access to the classification of the surface a scene is snapped to, the user must allow the app to access information about their surroundings. In your app’s `Info.plist` you should set `UIWantsDetailedSurfaceInfo` to `YES` and set `NSWorldSensingUsageDescription` to provide a description of why your app is requesting this information. The description will be displayed to the user when they first snap a scene from your app.

