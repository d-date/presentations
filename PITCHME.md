# Essential for what's new in Swift 4

by Daiki Matsudate / @d_date
---
## Daiki Matsudate / @d_date

- iOS Freelancer
- Realm News Translator
- CLEM Organizer
- WWDC17 Attendee

![profile.jpg](./res/profile.jpg)
---

![qiita.png](./res/qiita.png)

---
## Agenda

- Migration to Swift 4


---
## Migration to Swift 4

- [SE-0110] Distinguish between single-tuple and multiple-argument function types
- @objc inference

---
## [SE-0110] Distinguish between single-tuple and multiple-argument function types

``` swift
//Swift 3.1
let fn1 : (Int, Int) -> Void = { x in
    //Error: contextual closure type '(Int, Int) -> Void' expects 2 arguments, but 1 was used in closure body
}

//Swift 4
let fn2 : ((Int, Int, Int)) -> Int = { x in
    return x.0 + x.1 + x.2　//⭕
}

//Swift 3.1 and 4
let fn3 : (Int, Int, Int) -> Int = { x, y, z in
    return x + y + z //⭕
}
```
