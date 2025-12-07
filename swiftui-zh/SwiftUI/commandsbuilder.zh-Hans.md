---
来源： https://developer.apple.com/documentation/swiftui/commandsbuilder
抓取时间： 2025-12-04T13:23:25Z
---

# 命令生成器

**Structure**

用多表达式闭包构造命令集。与 `ViewBuilder` 一样，它支持在闭包主体中使用多达 10 个表达式。

### 声明

```swift
@resultBuilder struct CommandsBuilder
```

## 建设内容

- **buildBlock()**：从一个不含任何语句的程序块构建一个空命令集。
- **buildBlock(_:)**：通过修改传递作为子命令组写入的单个命令组。
- **buildBlock(_:_:)**
- **buildBlock(_:_:_:)**
- **buildBlock(_:_:_:_:)**
- **buildBlock(_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**

## 有条件地构建

- **buildEither(first:)**：当条件为真时，为多语句闭包中的条件语句生成内容。
- **buildEither(second:)**：当条件为假时，为多语句闭包中的条件语句生成内容。
- **buildIf(_:)**：为多语句闭包中的条件语句生成一个可选的 widget，该 widget 仅在条件求值为 true 时可见。
- **buildLimitedAvailability(_:)**：处理执行可用性检查的条件编译器控制语句的命令。
- **buildExpression(_:)**：在构建器中构建表达式。

## 定义命令

- **commands(content:)**：向场景添加命令。
- **commandsRemoved()**：删除修改后的场景定义的所有命令。
- **commandsReplaced(content:)**：用生成器中的命令替换已修改场景定义的所有命令。
- **Commands**：符合类型代表一组相关命令，可通过 macOS 的主菜单和 iOS 的按键命令向用户展示。
- **CommandMenu**：命令菜单是独立的顶级控件容器，用于执行相关的应用程序特定命令。
- **CommandGroup**：可添加到现有命令菜单的控件组。
- **CommandGroupPlacement**：您可以相对放置新命令组的标准位置。


---
source: https://developer.apple.com/documentation/swiftui/commandsbuilder
crawled: 2025-12-04T13:23:25Z
---

# CommandsBuilder

**Structure**

Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.

## Declaration

```swift
@resultBuilder struct CommandsBuilder
```

## Building content

- **buildBlock()**: Builds an empty command set from a block containing no statements.
- **buildBlock(_:)**: Passes a single command group written as a child group through modified.
- **buildBlock(_:_:)**
- **buildBlock(_:_:_:)**
- **buildBlock(_:_:_:_:)**
- **buildBlock(_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**

## Building conditionally

- **buildEither(first:)**: Produces content for a conditional statement in a multi-statement closure when the condition is true.
- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildIf(_:)**: Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.
- **buildLimitedAvailability(_:)**: Processes commands for a conditional compiler-control statement that performs an availability check.
- **buildExpression(_:)**: Builds an expression within the builder.

## Defining commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **Commands**: Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.
- **CommandMenu**: Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.
- **CommandGroup**: Groups of controls that you can add to existing command menus.
- **CommandGroupPlacement**: The standard locations that you can place new command groups relative to.

