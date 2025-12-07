---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventGesture
抓取时间： 2025-12-02T17:40:56Z
---

# 空间事件姿态

**Structure**

一种手势，可提供有关正在发生的空间事件（如点击和触摸）的信息。

## 声明

```swift
struct SpatialEventGesture
```

## 概览

使用这种类型的手势可跟踪多个同时发生的空间事件，并获取每个事件的详细信息。例如，您可以在[Canvas](Canvas.zh-Hans.md)中有正在发生的空间事件的每个位置放置一个粒子发射器：

```swift
struct ParticlePlayground: View {
    @State var model = ParticlesModel()

    var body: some View {
        Canvas { context, size in
            for particle in model.particles {
                context.fill(Path(ellipseIn: particle.frame),
                             with: .color(particle.color))
            }
        }
        .gesture(
            SpatialEventGesture()
                .onChanged { events in
                    for event in events {
                        if event.phase == .active {
                            // Update particle emitters.
                            model.emitters[event.id] = ParticlesModel.Emitter(
                                location: event.location
                            )
                        } else {
                            // Remove emitters when no longer active.
                            model.emitters[event.id] = nil
                        }
                    }
                }
                .onEnded { events in
                    for event in events {
                        // Remove emitters when no longer active.
                        model.emitters[event.id] = nil
                    }
                }
        )
    }
}
```

当检测到变化时，手势会提供一个[SpatialEventCollection](SpatialEventCollection.zh-Hans.md)结构。该集合包含 [Event](SpatialEventCollection/Event.zh-Hans.md) 值，代表正在发生的空间事件。每个事件都包含一个稳定、唯一的标识符，以便跟踪事件随时间的变化情况。事件还会显示其当前位置、时间戳、创建事件的输入设备的姿态以及其他有用信息。

集合中事件的阶段可以变为[ended](SpatialEventCollection/Event/Phase-swift_enum/ended.zh-Hans.md)或[cancelled](SpatialEventCollection/Event/Phase-swift_enum/cancelled.zh-Hans.md)，而手势本身仍处于活动状态。单独跟踪 [onChanged(_:)](Gesture/onChanged.zh-Hans.md) 或 [updating(_:body:)](Gesture/updating___body.zh-Hans.md) 中每个事件的状态，并清理 [onEnded(_:)](Gesture/onEnded.zh-Hans.md) 中的所有状态。



## 创建空间事件手势

- **init(coordinateSpace:)**：根据所需的坐标空间创建手势。

## 获取手势属性

- **coordinateSpace**：手势的坐标空间。

## 初始化器

- **init(coordinateSpace3D:)**：以所需的 3D 坐标空间创建手势。

## 识别空间事件

- **SpatialEventCollection**：针对特定视图的空间输入事件集合。
- **Chirality**：姿势的手性或手掌性。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventGesture
crawled: 2025-12-02T17:40:56Z
---

# SpatialEventGesture

**Structure**

A gesture that provides information about ongoing spatial events like clicks and touches.

## Declaration

```swift
struct SpatialEventGesture
```

## Overview

Use a gesture of this type to track multiple simultaneous spatial events and gain access to detailed information about each. For example, you can place a particle emitter at every location in a [Canvas](Canvas.zh-Hans.md) that has an ongoing spatial event:

```swift
struct ParticlePlayground: View {
    @State var model = ParticlesModel()

    var body: some View {
        Canvas { context, size in
            for particle in model.particles {
                context.fill(Path(ellipseIn: particle.frame),
                             with: .color(particle.color))
            }
        }
        .gesture(
            SpatialEventGesture()
                .onChanged { events in
                    for event in events {
                        if event.phase == .active {
                            // Update particle emitters.
                            model.emitters[event.id] = ParticlesModel.Emitter(
                                location: event.location
                            )
                        } else {
                            // Remove emitters when no longer active.
                            model.emitters[event.id] = nil
                        }
                    }
                }
                .onEnded { events in
                    for event in events {
                        // Remove emitters when no longer active.
                        model.emitters[event.id] = nil
                    }
                }
        )
    }
}
```

The gesture provides a [SpatialEventCollection](SpatialEventCollection.zh-Hans.md) structure when it detects changes. The collection contains [Event](SpatialEventCollection/Event.zh-Hans.md) values that represent ongoing spatial events. Each event contains a stable, unique identifier so that you can track how the event changes over time. The event also indicates its current location, a timestamp, the pose of the input device that creates it, and other useful information.

The phase of events in the collection can change to [ended](SpatialEventCollection/Event/Phase-swift_enum/ended.zh-Hans.md) or [cancelled](SpatialEventCollection/Event/Phase-swift_enum/cancelled.zh-Hans.md) while the gesture itself remains active. Individually track state for each event inside [onChanged(_:)](Gesture/onChanged.zh-Hans.md) or [updating(_:body:)](Gesture/updating___body.zh-Hans.md) and clean up all state in [onEnded(_:)](Gesture/onEnded.zh-Hans.md).



## Creating a spatial event gesture

- **init(coordinateSpace:)**: Creates the gesture with a desired coordinate space.

## Getting gesture properties

- **coordinateSpace**: The coordinate space of the gesture.

## Initializers

- **init(coordinateSpace3D:)**: Creates the gesture with a desired coordinate space 3D.

## Recognizing spatial events

- **SpatialEventCollection**: A collection of spatial input events that target a specific view.
- **Chirality**: The chirality, or handedness, of a pose.

## Conforms To

- Gesture

