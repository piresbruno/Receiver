# Receiver

<a href="https://github.com/Carthage/Carthage"><img src="https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat"></a>
[![Swift 3.0](https://img.shields.io/badge/Swift-4.0-orange.svg?style=flat)](https://developer.apple.com/swift/)
[![License MIT](https://img.shields.io/badge/License-MIT-lightgrey.svg?style=flat)](https://opensource.org/licenses/MIT)


---

As a [ReactiveSwift](https://github.com/ReactiveCocoa/ReactiveSwift) user myself, most of time, it's difficult to convince someone to just simply start using it. The reality is that most codebases are not suitable to just adopt it:

1. Fear of a big dependency
2. The learning curve
3. Adapting the current codebase to a FRP mindset/approach.

Nevertheless, a precious pattern can still be used, even without such an awesome lib like [ReactiveSwift](https://github.com/ReactiveCocoa/ReactiveSwift). 😖

### 🌈 Enter `Receiver`! 🌈

![](https://viralviralvideos.com/wp-content/uploads/GIF/2015/06/OMG-this-is-so-awesome-GIF.gif)

`Receiver` is nothing more than an opiniated implementation of the [Observer pattern](https://en.wikipedia.org/wiki/Observer_pattern). Or, if you prefer, [`FRP`](https://en.wikipedia.org/wiki/Functional_reactive_programming) without the `F` and a really small `R` ([rP](https://en.wikipedia.org/wiki/Reactive_programming) 🤔). 

### Show me the codez! 😸

Let's begin with the basics. **There are three methods in total**. Yup, that's right. 

#### 1. Creating the Receiver

```
let (transmitter, receiver) = Receiver<Int>.make()
```

A `receiver` can never be created without an associated `transmitter` (what good would that be?)

#### 2. Listening to an event 📡

This is how you observe events:

```
receiver.listen { wave in print("Can I haz \(wave) cheezburger. 🐈") }
```

#### 3. Broadcasting an event 📻

This is how you send events:

```
transmitter.broadcast(1)
```

### Ok, so why would I use this? 🤷‍♀️

~Well, to make your codebase awesome of course.~ There are a lot of places where the observer pattern can be useful. In the most simplistic scenario, when delegation is not good enough and you have an `1-to-N` relationship.
