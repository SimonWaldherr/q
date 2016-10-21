# q

q is a better way to do print statement debugging.

Type `q.Q` instead of `fmt.Printf` and your variables will be printed like this:

![q output examples](https://i.imgur.com/OFmm7pb.png)

## Why is this better than `fmt.Printf`?

* Faster to type
* Pretty-printed vars and expressions
* Easier to see inside structs
* Doesn't go to noisy-ass stdout. It goes to `/tmp/q`.
* Pretty colors!

## Basic Usage

```go
import "github.com/y0ssar1an/q"
...
q.Q(a, b, c)

// Alternatively, use the . import and you can omit the package name.
// q only exports the Q function.
import . "github.com/y0ssar1an/q"
...
Q(a, b, c)
```

For best results, dedicate a terminal to tailing `/tmp/q` while you work.

## Install

```sh
go get -u github.com/y0ssar1an/q
```

Put this alias in your shell config. Typing `qq` will then start tailing
`/tmp/q`.
```sh
alias qq=". $GOPATH/src/github.com/y0ssar1an/q/q.sh"
```

## Haven't I seen this somewhere before?

Python programmers will recognize this as a Golang port of the awesome
[`q` module by zestyping](https://github.com/zestyping/q).

Ping does a great job of explaining `q` in his awesome lightning talk from
PyCon 2013. Watch it! It's funny!

[![ping's PyCon 2013 lightning talk](https://i.imgur.com/7KmWvtG.jpg)](https://youtu.be/OL3De8BAhME?t=25m14s)

## FAQ

### Why `q.Q`?
It's quick to type and unlikely to cause naming collisions.

### Is `q.Q()` concurrency safe?
Yes
