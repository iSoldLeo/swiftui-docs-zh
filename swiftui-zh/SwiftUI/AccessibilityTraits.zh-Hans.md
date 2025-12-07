---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityTraits
抓取时间： 2025-12-02T17:44:25Z
---

# 可访问性特征

**Structure**

一组可访问性特征，用于描述元素的行为方式。

### 声明

```swift
struct AccessibilityTraits
```

## 获取特征

- **allowsDirectInteraction**：无障碍元素允许 VoiceOver 用户进行直接触摸交互。
- **causesPageTurn**：当 VoiceOver 读完其中的文本时，辅助功能元素会自动翻页。
- **isButton**：辅助功能元素是一个按钮。
- **isHeader**：无障碍元素是一个按钮：无障碍元素是将内容划分为不同部分的标题，如导航栏的标题。
- **isImage**：无障碍元素是图像。
- **isKeyboardKey**：辅助功能元素的行为类似于键盘按键。
- **isLink**：辅助功能元素是一个链接。
- **isModal**：可访问性元素是模态的。
- **isSearchField**：辅助功能元素是搜索字段。
- **isSelected**：当前已选择无障碍元素。
- **isStaticText**：辅助功能元素是静态文本，用户无法修改。
- **isSummaryElement**：辅助功能元素在应用程序启动时提供摘要信息。
- **isToggle**：辅助功能元素是一个切换按钮。
- **playsSound**：辅助功能元素是一个切换器：无障碍元素在激活时会播放自己的声音。
- **startsMediaSession**：辅助功能元素被激活时会启动媒体会话。
- **updatesFrequently**：辅助功能元素经常更新其标签或值。

### 类型属性

- **isTabBar**：辅助功能元素是一个标签栏。

## 为内容指定属性

- **accessibilityAddTraits(_:)**：为视图添加给定的特质。
- **accessibilityRemoveTraits(_:)**：从该视图中删除给定性状。

## 符合

- 等价
- 可表达数组字素
- 可发送
- 可发送元类型
- 集合代数


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityTraits
crawled: 2025-12-02T17:44:25Z
---

# AccessibilityTraits

**Structure**

A set of accessibility traits that describe how an element behaves.

## Declaration

```swift
struct AccessibilityTraits
```

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
- **startsMediaSession**: The accessibility element starts a media session when it is activated.
- **updatesFrequently**: The accessibility element frequently updates its label or value.

## Type Properties

- **isTabBar**: The accessibility element is a tab bar.

## Assigning traits to content

- **accessibilityAddTraits(_:)**: Adds the given traits to the view.
- **accessibilityRemoveTraits(_:)**: Removes the given traits from this view.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- Sendable
- SendableMetatype
- SetAlgebra

