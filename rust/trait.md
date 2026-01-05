---
id: 1767460197-OJJA
aliases: []
tags: []
---

# Trait

`Trait` in rust are like interfaces in Java. They allow us to define common
behaviour on our data type. Contrary to Java with trait we can only define
method / function not variable

## Writting trait

```rust
pub trait Summary {
    fn summarize(&self) -> String;
}
```

We have define custom trait that we can implement on our data type like a
`Book`. This trait telle us that the data type that use it have a `summarize`
method that return us a `String`

## Implementing trait

```rust
pub struct Book {
    content: String
}

impl Summary for Book {
    fn summarize(&self) -> String {
        self.content
    }
}
```

We implement a trait on a data type by using the `impl` keyword then the name of
the trait that we want to implement then the `for` keyword and we finish the the
name of the data type

We can implement a trait on a type only once

## Scope

Like custom data type our traits are only available in the module / crates where
they are define. If we want to allow other crates to use it we need to make it
public and to import it

## Default 

We can provide default implementation for our method by implemting them on the
trait and by not redefining them on our data type trait implementation

```rust
trait Summary {
    fn summarize(&self) -> String {
        "summary".to_string()
    }
}

impl Summary for Book {}
```

## Trait and generic

It's not possible to implement a trait multiple time on the same type except if
the trait use a generic parameter

**example**: Let's say we are creating a game. In our game the player will need to
move but there is different way to move : Walk, Train, Car

```rust
struct Car {}
struct Train {}
struct Walk {}

struct Player {}

trait Move<T> {
    fn move(&self) {}
}
```

If we want our player to move with the car, the train or by walking we will need
to specify all the trait implementation

```rust
impl Move<Car> for Player {}
impl Move<Train> for Player {}
impl Move<Walk> for Player {}
```

Now if we want to move we will need to specify when calling the `move` method
which implementation of the trait we want to use

```rust
player.move::<Car>();
```

## Trait as parameter

We can provide data type as parameter on function but we can also use trait to
required that our parameter implement some behaviour

```rust
fn summary_content(content: impl Summary) -> String {
    content.summarize()
}
```

This function accept all data type that implement the `Summary` trait

## Trait bound

Specifyng a trait as parameter in a function is call a `trait bound`. That means
that we restrict all possible parameter to those that have the correct trait

The `impl Trait` syntax is simple to use and work perfectly for easy case but in
reality it's syntatic sugar for the trait bound

When the rust compiler see this it compiles it to this longer form

```rust
fn summary_content<T : Summary>(content: T) -> String {
    content.summarize()
}
```

This form allow us to write more complexe case

For exemple if our function need multiple parameter instead of having this

```rust
fn summary_content(content_a: impl Summary, content_b impl Summary) -> String {}
```

We can use the trait bound syntax to simplify it


```rust
fn summary_content<T: Summary>(content_a: T, content_b T) -> String {}
```

### Multiple Trait bound

We can specify mulitple trait bound with the `+` syntaxt

```rust
fn summary_content<T: Summary + Author>(content_a: T) -> String {}
```

In this case our data type need to implement the Summary trait and the Author
Trait

### Simplfying trait bound with Where

If there is too many trait bound it can be hard to read it. To simplify this
case we can use the `Where` syntax

```rust
fn summary_content<T>(content_a: T) -> String where T: Summary + Author {}
```

## Trait as return type

We can specify Trait as parameter but also as return type. This mean that we can
specify which behaviour our return data type implements

```rust
fn return_summarizable() -> impl Summary {}
```

## Conditional trait

We can implement trait on a data type conditionally if the data type already
implement a specific trait

```rust
impl<T: Summary> Print <T>{
    fn print(&self) {
        println(self.summarize())
    }
}
```

In this exemple we can only implement the Print trait on a data type that
implement the Summary trait

## Associated type

Associated types allow using a placeholder type to use it in the trait's method
definition

It's the implementor of a trait that will specify which concrete type to use.

The associated type allow to use the the type to be used in the method's
definitions without knowing it

A good exemple of an associated type in a trait its the `Iterator` trait

```rust
pub trait Iterator {
    type Item;

    fn next(&mut self) -> Option<Self::Item>;
}
```

The `Item` type is an associated type. In this case it's use in the `next`
method definition. With this we know that the `next` method return a value of
the type `Option<Self::Item>`

When we implement the Iterator trait on a concrete type we will need to specify
what concrete type will replace `Item`

**example**: We want to implement the Iterator trait for a Counter

```rust
struct Counter {
    count: u32,
}

impl Counter {
    fn new() -> Counter {
        Counter { count: 0 }
    }
}

impl Iterator for Counter {
    type Item = u32;

    fn next(&mut self) -> Option<Self::Item> {
        // --snip--
        if self.count < 5 {
            self.count += 1;
            Some(self.count)
        } else {
            None
        }
    }
}
```

In this example `Item` is replace with `u32` so that means that when we call
`next` on Counter it will always return a `Option<u32>`

We could use generic instead

```rust
pub trait Iterator<T> {
    fn next(&mut self) -> Option<T>;
}
```

The downside of this is because `T` can be a multiple of different type (it
could be `String`, `bool`, `u32`...) we need to implement all the different possibilites

```rust
Iterator<String> for Counter;
Iterator<u32> for Counter;
Iterator<bool> for Counter;
```

With this each time we call the `next` method we will need to provide the right type
annotation to specify which implementation we need to use

Associated type don't have this problem because we can't implement a trait on a
type multiple type.

Furthermore the associated type is now part of the trait which mean the
implementor of the trait must provide a concrete type for the trait
