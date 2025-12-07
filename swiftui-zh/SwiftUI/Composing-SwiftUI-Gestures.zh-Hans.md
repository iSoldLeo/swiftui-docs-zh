---
来源： https://developer.apple.com/documentation/SwiftUI/Composing-SwiftUI-Gestures
抓取时间： 2025-12-02T17:41:10Z
---

# 组成 SwiftUI 手势

**Article**

组合手势以创建复杂的交互。

## 概览

当您在应用程序的视图层次结构中添加多个手势时，您需要决定这些手势之间的交互方式。您可以使用手势组合来定义 SwiftUI 识别手势的顺序。有三种手势组合类型：

- 同时
- 顺序
- 独家

同时组合手势修饰符时，SwiftUI 必须同时识别所有子手势模式，才能识别组合手势。当您一个接一个地排列手势修饰符时，SwiftUI 必须按顺序识别每个子手势。最后，当您完全组合手势时，当 SwiftUI 只识别一个子手势而不识别其他手势时，SwiftUI 会识别整个手势模式。

### 一个手势接一个手势的顺序

当您一个手势接一个手势地排列时，SwiftUI 会先识别第一个手势，然后再识别第二个手势。例如，若要在用户拖动视图之前要求长按，则需要在[DragGesture](DragGesture.zh-Hans.md)之后排序[LongPressGesture](LongPressGesture.zh-Hans.md)。

#### 按顺序排列的手势状态模型

为了更容易跟踪复杂的状态，可以使用一个枚举来捕获配置视图所需的所有状态。在下面的示例中，有三种重要状态：无交互（`inactive`）、正在长按（`pressing`）和拖动（`dragging`）。

```swift
struct DraggableCircle: View {

    enum DragState {
        case inactive
        case pressing
        case dragging(translation: CGSize)
        
        var translation: CGSize {
            switch self {
            case .inactive, .pressing:
                return .zero
            case .dragging(let translation):
                return translation
            }
        }
        
        var isActive: Bool {
            switch self {
            case .inactive:
                return false
            case .pressing, .dragging:
                return true
            }
        }
        
        var isDragging: Bool {
            switch self {
            case .inactive, .pressing:
                return false
            case .dragging:
                return true
            }
        }
    }
    
    @GestureState private var dragState = DragState.inactive
    @State private var viewState = CGSize.zero
```

#### 创建手势并更新用户界面状态

当您对两个手势进行排序时，回调会捕捉两个手势的状态。在更新回调中，新的`value`使用枚举来表示可能的手势状态组合。下面的代码将底层手势状态转换为上面定义的高级`DragState`枚举。

```swift
var body: some View {
        let minimumLongPressDuration = 0.5
        let longPressDrag = LongPressGesture(minimumDuration: minimumLongPressDuration)
            .sequenced(before: DragGesture())
            .updating($dragState) { value, state, transaction in
                switch value {
                // Long press begins.
                case .first(true):
                    state = .pressing
                // Long press confirmed, dragging may begin.
                case .second(true, let drag):
                    state = .dragging(translation: drag?.translation ?? .zero)
                // Dragging ended or the long press cancelled.
                default:
                    state = .inactive
                }
            }
            .onEnded { value in
                guard case .second(true, let drag?) = value else { return }
                self.viewState.width += drag.translation.width
                self.viewState.height += drag.translation.height
            }
```

当用户开始长按视图时，拖动状态会变为 `pressing`，并在形状下方显示阴影动画。当用户完成长按，拖动状态变为 `dragging`后，形状周围会出现一个边框，表示用户可以开始移动视图。

```swift
        return Circle()
            .fill(Color.blue)
            .overlay(dragState.isDragging ? Circle().stroke(Color.white, lineWidth: 2) : nil)
            .frame(width: 100, height: 100, alignment: .center)
            .offset(
                x: viewState.width + dragState.translation.width,
                y: viewState.height + dragState.translation.height
            )
            .animation(nil)
            .shadow(radius: dragState.isActive ? 8 : 0)
            .animation(.linear(duration: minimumLongPressDuration))
            .gesture(longPressDrag)
    }
}
```

## 组合手势

- **simultaneousGesture(_:including:)**：将手势附加到视图，以便与视图定义的手势同时处理。
- **simultaneousGesture(_:isEnabled:)**：将手势附加到视图，以便与视图定义的手势同时处理。
- **simultaneousGesture(_:name:isEnabled:)**：将手势附加到视图，以便与视图定义的手势同时处理。
- **SequenceGesture**：由两个手势组成的手势序列。
- **SimultaneousGesture**：包含两个手势的手势，这两个手势可以同时出现，但都不在另一个手势之前。
- **ExclusiveGesture**：由两个手势组成的手势，其中只有一个手势可以成功。


---
source: https://developer.apple.com/documentation/SwiftUI/Composing-SwiftUI-Gestures
crawled: 2025-12-02T17:41:10Z
---

# Composing SwiftUI gestures

**Article**

Combine gestures to create complex interactions.

## Overview

When you add multiple gestures to your app’s view hierarchy, you need to decide how the gestures interact with each other. You use gesture composition to define the order SwiftUI recognizes gestures. There are three gesture composition types:

- Simultaneous
- Sequenced
- Exclusive

When you combine gesture modifiers simultaneously, SwiftUI must recognize all subgesture patterns at the same time for it to recognize the combining gesture. When you sequence gesture modifiers one after the other, SwiftUI must recognize each subgesture in order. Finally, when you combine gestures exclusively, SwiftUI recognizes the entire gesture pattern when SwiftUI only recognizes one subgesture but not the others.

### Sequence one gesture after another

When you sequence one gesture after another, SwiftUI recognizes the first gesture before it recognizes the second. For example, to require a long press before the user can drag a view, you sequence a [DragGesture](DragGesture.zh-Hans.md) after a [LongPressGesture](LongPressGesture.zh-Hans.md).

#### Model sequenced gesture states

To make it easier to track complicated states, use an enumeration that captures all of the states you need to configure your views. In the following example, there are three important states: no interaction (`inactive`), long press in progress (`pressing`), and dragging (`dragging`).

```swift
struct DraggableCircle: View {

    enum DragState {
        case inactive
        case pressing
        case dragging(translation: CGSize)
        
        var translation: CGSize {
            switch self {
            case .inactive, .pressing:
                return .zero
            case .dragging(let translation):
                return translation
            }
        }
        
        var isActive: Bool {
            switch self {
            case .inactive:
                return false
            case .pressing, .dragging:
                return true
            }
        }
        
        var isDragging: Bool {
            switch self {
            case .inactive, .pressing:
                return false
            case .dragging:
                return true
            }
        }
    }
    
    @GestureState private var dragState = DragState.inactive
    @State private var viewState = CGSize.zero
```

#### Create gestures and update the UI state

When you sequence two gestures, the callbacks capture the state of both gestures. In the update callback, the new `value` uses an enumeration to represent the combination of the possible gesture states. The code below converts the underlying gesture states into the high-level `DragState` enumeration defined above.

```swift
var body: some View {
        let minimumLongPressDuration = 0.5
        let longPressDrag = LongPressGesture(minimumDuration: minimumLongPressDuration)
            .sequenced(before: DragGesture())
            .updating($dragState) { value, state, transaction in
                switch value {
                // Long press begins.
                case .first(true):
                    state = .pressing
                // Long press confirmed, dragging may begin.
                case .second(true, let drag):
                    state = .dragging(translation: drag?.translation ?? .zero)
                // Dragging ended or the long press cancelled.
                default:
                    state = .inactive
                }
            }
            .onEnded { value in
                guard case .second(true, let drag?) = value else { return }
                self.viewState.width += drag.translation.width
                self.viewState.height += drag.translation.height
            }
```

When the user begins pressing the view, the drag state changes to `pressing` and a shadow animates under the shape. After the user finishes the long press and the drag state changes to `dragging`, a border appears around the shape to indicate that the user may begin moving the view.

```swift
        return Circle()
            .fill(Color.blue)
            .overlay(dragState.isDragging ? Circle().stroke(Color.white, lineWidth: 2) : nil)
            .frame(width: 100, height: 100, alignment: .center)
            .offset(
                x: viewState.width + dragState.translation.width,
                y: viewState.height + dragState.translation.height
            )
            .animation(nil)
            .shadow(radius: dragState.isActive ? 8 : 0)
            .animation(.linear(duration: minimumLongPressDuration))
            .gesture(longPressDrag)
    }
}
```

## Combining gestures

- **simultaneousGesture(_:including:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:name:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **SequenceGesture**: A gesture that’s a sequence of two gestures.
- **SimultaneousGesture**: A gesture containing two gestures that can happen at the same time with neither of them preceding the other.
- **ExclusiveGesture**: A gesture that consists of two gestures where only one of them can succeed.

