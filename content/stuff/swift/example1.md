---
title: WWDC 2019
linktitle: WWDC 201911
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
diagram: true
menu:
  swift:
    parent: swift
    weight: 1

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---

Here i want to share a bit of what i have learned 

this years WWDC had tons of new stuff to sort out.

the hardest thing for me personaly was and is to realy free your mind for some new concepts and not stick to old patterns and try to find them in the new world of SwiftUI Combine and more.

Many of those things are confusing on first sight. Maybe it's my age or the fact that i am not a native speaker :-D ... but honestly i am confused by sentences like :

> "the subscriber calls subcribe **with** the subcriber **to** the publisher... ataching it"

> "then the Publisher will send a subscription to the subcriber which the subcriber will use to make a request from the publisher"

like many things in life it makes most sense when you already got it.

so first have a look at the official apple resource to get a better understaning about those topic. And don't feel ashamed to watch a video twice... try something out... and watch it again after one or two weeks... you'll learn and understand more with each iteration.

# Some good stops to reference

## Modern Swift API Design

[Modern Swift API Design](https://developer.apple.com/videos/play/wwdc2019/415/)

Every programming language has a set of conventions that people come to expect. Learn about the patterns that are common to Swift API design, with examples from new APIs like SwiftUI, Combine, and RealityKit. Whether you're developing an app as part of a team, or you're publishing a library for others to use, find out how to use new features of Swift to ensure clarity and correct use of your APIs

# Some terminology

## Combine

### Operator

an `Operator` converts values from a publisher to a subcriber

an `Operator` again is a Publisher on its own

```swift
# Example of code highlighting
    var name: String {
        didSet {
            tank.name = name
            try! tank.managedObjectContext?.save()
            didChange.send(())
        }
    }
```

{{< highlight Swift >}}
    var name: String {
        didSet {
            tank.name = name
            try! tank.managedObjectContext?.save()
            didChange.send(())
        }
    }
{{< /highlight >}}

### upstream

when subcribers send to a `Publisher`

{{< diagram >}}
graph LR;
    A[subcribers] -->|upstream| B(Publisher)
{{< /diagram >}}


### downstream

when publisher send to a `Subcriber`

{{< diagram >}}
graph LR;
    A[Publisher] -->|downstream| B(subscriber)
{{< /diagram >}}
