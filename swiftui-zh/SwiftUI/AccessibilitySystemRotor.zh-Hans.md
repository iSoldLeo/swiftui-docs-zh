---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilitySystemRotor
抓取时间： 2025-12-02T17:44:36Z
---

# 无障碍系统

**Structure**

指定一个转子，用一个开发者提供的转子替换一个自动的、系统提供的转子。

### 声明

```swift
struct AccessibilitySystemRotor
```

## 迭代文本

- **textFields**：系统旋转器允许用户遍历所有文本字段。
- **boldText**：允许用户遍历所有粗体文本范围的系统旋转器。
- **italicText**：**italicText**: 允许用户遍历斜体文本所有范围的系统旋转器。
- **underlineText**：允许用户遍历所有下划线文本范围的系统旋转器。
- **misspelledWords**：允许用户遍历所有拼写错误单词范围的系统旋转器。

## 遍历标题

- **headings**：允许用户遍历所有标题的系统旋转器。
- **headings(level:)**：允许用户遍历不同标题级别的所有标题的系统旋转器。

## 通过链接迭代

- **links**：允许用户遍历所有链接的系统旋转器。
- **links(visited:)**：允许用户遍历链接或已访问链接的系统旋转器。

## 通过其他元素迭代

- **images**：允许用户遍历所有图像的系统旋转器。
- **landmarks**：允许用户遍历所有地标的系统旋转器。
- **lists**：允许用户遍历所有列表的系统旋转器。
- **tables**：允许用户遍历所有表格的系统旋转器。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilitySystemRotor
crawled: 2025-12-02T17:44:36Z
---

# AccessibilitySystemRotor

**Structure**

Designates a Rotor that replaces one of the automatic, system-provided Rotors with a developer-provided Rotor.

## Declaration

```swift
struct AccessibilitySystemRotor
```

## Iterating through text

- **textFields**: System Rotor allowing users to iterate through all text fields.
- **boldText**: System Rotor allowing users to iterate through all the ranges of bolded text.
- **italicText**: System Rotor allowing users to iterate through all the ranges of italicized text.
- **underlineText**: System Rotor allowing users to iterate through all the ranges of underlined text.
- **misspelledWords**: System Rotor allowing users to iterate through all the ranges of mis-spelled words.

## Iterating through headings

- **headings**: System Rotor allowing users to iterate through all headings.
- **headings(level:)**: System Rotors allowing users to iterate through all headings, of various heading levels.

## Iterating through links

- **links**: System Rotor allowing users to iterate through all links.
- **links(visited:)**: System Rotors allowing users to iterate through links or visited links.

## Iterating through other elements

- **images**: System Rotor allowing users to iterate through all images.
- **landmarks**: System Rotor allowing users to iterate through all landmarks.
- **lists**: System Rotor allowing users to iterate through all lists.
- **tables**: System Rotor allowing users to iterate through all tables.

## Conforms To

- Sendable
- SendableMetatype

