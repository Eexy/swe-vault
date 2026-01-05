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

