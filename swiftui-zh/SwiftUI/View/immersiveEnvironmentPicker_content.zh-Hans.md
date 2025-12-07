--- 来源：https://developer.apple.com/documentation/SwiftUI/View/immersiveEnvironmentPicker(content:)

抓取时间：2025-11-30T20:07:27Z

---

# immersiveEnvironmentPicker(content:)

**实例方法**

在媒体播放器的环境选择器中添加菜单项，以打开沉浸式空间。

## 声明

```swift
nonisolated func immersiveEnvironmentPicker<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## 讨论

这些菜单项会添加到最近使用过的系统环境旁边。

```swift
SystemPlayerView(player: player)
    .immersiveEnvironmentPicker {
        Button("Chalet", systemImage: "fireplace") {
            Task {
                await openImmersiveSpace(id: "Chalet")
            }
        }
    }
```

使用 [UIViewControllerRepresentable](../UIViewControllerRepresentable.zh-Hans.md) 实例在 SwiftUI 界面中显示 [doc://com.apple.documentation/documentation/AVKit/AVPlayerViewController] 类。

```swift
struct SystemPlayerView: UIViewControllerRepresentable {
    let player: AVPlayer

    func makeUIViewController(context: Context) -> AVPlayerViewController {
        return AVPlayerViewController()
    }

    func updateUIViewController(_ avPlayerViewController: AVPlayerViewController, context: Context) {
        viewController.player = player
    }
}
```

物品将捐赠给层级结构下游的媒体播放器（例如 [doc://com.apple.documentation/documentation/AVKit/AVPlayerViewController]）。


---
source: https://developer.apple.com/documentation/SwiftUI/View/immersiveEnvironmentPicker(content:)
crawled: 2025-11-30T20:07:27Z
---

# immersiveEnvironmentPicker(content:)

**Instance Method**

Add menu items to open immersive spaces from a media player’s environment picker.

## Declaration

```swift
nonisolated func immersiveEnvironmentPicker<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## Discussion

These items are added alongside recently used system environments.

```swift
SystemPlayerView(player: player)
    .immersiveEnvironmentPicker {
        Button("Chalet", systemImage: "fireplace") {
            Task {
                await openImmersiveSpace(id: "Chalet")
            }
        }
    }
```

Use a [UIViewControllerRepresentable](../UIViewControllerRepresentable.zh-Hans.md) instance to display a [doc://com.apple.documentation/documentation/AVKit/AVPlayerViewController] class in your SwiftUI interface.

```swift
struct SystemPlayerView: UIViewControllerRepresentable {
    let player: AVPlayer

    func makeUIViewController(context: Context) -> AVPlayerViewController {
        return AVPlayerViewController()
    }

    func updateUIViewController(_ avPlayerViewController: AVPlayerViewController, context: Context) {
        viewController.player = player
    }
}
```

Items will be donated to media players (like [doc://com.apple.documentation/documentation/AVKit/AVPlayerViewController]) downstream in the hierarchy.



