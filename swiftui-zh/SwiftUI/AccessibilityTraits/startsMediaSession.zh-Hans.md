---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityTraits/startsMediaSession
抓取时间： 2025-12-03T06:49:54Z
---

# startsMediaSession

**类型属性**

无障碍元素在激活时会启动媒体会话。

## 声明

```swift
static let startsMediaSession: AccessibilityTraits
```

## 讨论

在不应被中断的媒体会话期间，使用此特性可关闭 VoiceOver 等辅助技术的音频输出。例如，当用户正在录制音频时，您可以使用此特性来静音 VoiceOver 语音。

## 获取特征

- **allowsDirectInteraction**：无障碍元素允许 VoiceOver 用户进行直接触摸交互。
- **causesPageTurn**：当 VoiceOver 读完其中的文本时，辅助功能元素会自动翻页。
- **isButton**：辅助功能元素是一个按钮。
- **isHeader**：无障碍元素是将内容划分为不同部分的标题，如导航栏的标题。
- **isImage**：无障碍元素是图像。
- **isKeyboardKey**：辅助功能元素的行为类似于键盘按键。
- **isLink**：辅助功能元素是一个链接。
- **isModal**：可访问性元素是模态的。
- **isSearchField**：辅助功能元素是搜索字段。
- **isSelected**：当前已选择无障碍元素。
- **isStaticText**：辅助功能元素是静态文本，用户无法修改。
- **isSummaryElement**：辅助功能元素在应用程序启动时提供摘要信息。
- **isToggle**：辅助功能元素是一个切换按钮。
- **playsSound**：无障碍元素在激活时会播放自己的声音。
- **updatesFrequently**：辅助功能元素经常更新其标签或值。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityTraits/startsMediaSession
crawled: 2025-12-03T06:49:54Z
---

# startsMediaSession

**Type Property**

The accessibility element starts a media session when it is activated.

## Declaration

```swift
static let startsMediaSession: AccessibilityTraits
```

## Discussion

Use this trait to silence the audio output of an assistive technology, such as VoiceOver, during a media session that should not be interrupted. For example, you might use this trait to silence VoiceOver speech while the user is recording audio.

## Getting traits

- **allowsDirectInteraction**: The accessibility element allows direct touch interaction for VoiceOver users.
- **causesPageTurn**: The accessibility element causes an automatic page turn when VoiceOver finishes reading the text within it.
- **isButton**: The accessibility element is a button.
- **isHeader**: The accessibility element is a header that divides content into sections, like the title of a navigation bar.
- **isImage**: The accessibility element is an image.
- **isKeyboardKey**: The accessibility element behaves as a keyboard key.
- **isLink**: The accessibility element is a link.
- **isModal**: The accessibility element is modal.
- **isSearchField**: The accessibility element is a search field.
- **isSelected**: The accessibility element is currently selected.
- **isStaticText**: The accessibility element is a static text that cannot be modified by the user.
- **isSummaryElement**: The accessibility element provides summary information when the application starts.
- **isToggle**: The accessibility element is a toggle.
- **playsSound**: The accessibility element plays its own sound when activated.
- **updatesFrequently**: The accessibility element frequently updates its label or value.

