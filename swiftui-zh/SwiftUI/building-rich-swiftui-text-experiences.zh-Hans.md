---

来源：https://developer.apple.com/documentation/SwiftUI/building-rich-swiftui-text-experiences
抓取时间：2025-12-02T15:45:18Z

---

# 构建富文本 SwiftUI 体验

**示例代码**

使用 SwiftUI 文本编辑器视图和属性字符串构建一个格式化文本编辑器。

## 概述

您可以跟随 WWDC25 会议中编写的代码进行学习，了解如何将 `TextEditor` 升级为富文本，构建自定义控件，以及限制编辑器提供的格式选项。

完成代码学习后，您可以进一步了解如何使用 SwiftData 持久化富文本，以及如何使用 `Transferable` 协议导出富文本文档。

### 配置示例代码项目

要在 Xcode 中配置示例代码项目，请执行以下操作：

1. 使用最新版本的 Xcode 打开示例。

2. 将开发者团队设置为允许 Xcode 自动管理配置文件。有关更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/preparing-your-app-for-distribution#Set-the-bundle-ID] 和 [doc://com.apple.documentation/documentation/Xcode/preparing-your-app-for-distribution#Assign-the-project-to-a-team]。

## 获取文本输入

- **TextField**：显示可编辑文本界面的控件。

- **textFieldStyle(_:)**：设置此视图中文本字段的样式。

- **SecureField**：用户可安全地输入私密文本的控件。

- **TextEditor**：可显示和编辑长文本的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/building-rich-swiftui-text-experiences
crawled: 2025-12-02T15:45:18Z
---

# Building rich SwiftUI text experiences

**Sample Code**

Build an editor for formatted text using SwiftUI text editor views and attributed strings.

## Overview



You can follow along with the code written in the WWDC25 session, learning how to upgrade `TextEditor` to rich text, build custom controls, and constrain the formatting options the editor provides.

After the code-along, you can learn more about how to persist rich text using SwiftData, and how to export rich text documents using the `Transferable` protocol.

### Configure the sample code project

To configure the sample code project, do the following in Xcode:

1. Open the sample with the latest version of Xcode.
2. Set the developer team to let Xcode automatically manage the provisioning profile. For more information, see [doc://com.apple.documentation/documentation/Xcode/preparing-your-app-for-distribution#Set-the-bundle-ID] and [doc://com.apple.documentation/documentation/Xcode/preparing-your-app-for-distribution#Assign-the-project-to-a-team].

## Getting text input

- **TextField**: A control that displays an editable text interface.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **SecureField**: A control into which people securely enter private text.
- **TextEditor**: A view that can display and edit long-form text.

