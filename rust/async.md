---
id: async
aliases: []
tags: []
---
# Async

There is 2 possibilites in rust to do operations that take a lot of time without
blocking the current process

- parallelism
- concurrency

## Parallelism & Concurrency

Parallelism and concurrency are two differents approach to make long operations,
multitasks and to speed up our program

### Parallelism

With parallelism we split operations among our cpu's cores. That means that each
core with handle one 

**exemple** : If we have a group of person that must complete a list of tasks
with parallelism each person will handle a different tasks

### Concurrency

With concurrency we alternate between the different operation, task.

**exemple** : If one personne must handle a set of tasks instead of doing all of
them one by one he can do some stuff on the first tasks, then switching on task
2 then go back to task 1 and then swith to a third task to go back on task 2
after

### Mixing the two

Parallelism and concurrency are not totally disjoint approach. If you need /
want you can mix them to gain efficiency

**exemple** : Let say you have a group of person that must complete a list of
tasks. One of the person need that a task A and B must be done to start its task C. In
this situation the person that handle A and B will alternate between A and B
while the rest of the group will handle their tasks. When A and B are done task
C can start

## Asynchronous programming

Asynchronous programming is when our program using concurrency to handle
different task

## Future

A future represent a value / data which is not ready now but will be later (Same as
Promise in JS) 

To work with future rust provide a Future [[trait]]. This trait provide a common
interface to work with asynchronous operation (operation that return a future) that implement different data structures

So in rust a future is simply a type that implement the Future trait

Each future hold its own information about the progress that been made and what
"ready" mean

## Async / await syntax

`async` and `await` are two keyword in rust that simplify writing async
operation and working with future.
We can find this syntax in other language like JS or C#

```rust
async fn make_api_request() -> Option<String> {
    let res = api_request().await;
    res
}

```

### Async

The `async` can be apply to a block or a function that indicate that this return a
future. Which mean that it's indicate that the block / function can be
interrupted / resumed

### Await

The `await` keyword indicate that we need to wait the completion
of the future. We are waiting for the operation to be done. When we use the
`await` keyword our program will no go to the next line before the future is done completed

The `await` keyword can only be use in a block / function that is mark with the
`async` keyword

### Compiled async / await syntax

`async` and `await` are synthetic sugar to simplify writing asynchronous
operations.

Once compile an async block is compile into a block that return an unique anonymous data type
that implements the Future trait with an associated type `Output`

When the compiler find an async function it compiles it into a non async
function whose body is an async block thus an async function's return type is the type of
the anonymous data type the compiler creates for that async block.

```rust
fn make_api_request() -> impl Future<Output = Option<String>> {
    async  {
        let res = api_request().await;
        res
    }
}
```

The compiler can decide to use either `async` or `async move` depending of the
situation


## Runtime

To do asynchronous programming and work with future in rust we need a runtime. The
runtime will dictate how to handle future, how to pause when there is an `await` keyword, how to switch between tasks...

Most of programming language that implement asynchronous programming come with
their runtime like JS or C#. In rust we need to implement it ourselve or to use
an exisitng one. This allow developpers to craft / choose a runtime specific
to their usecase

For exemple imagine 2 servers. One powerful server with 24 core and a lot of ram
and a small server with 1 core. To use the most of those 2 servers we
can't use the same runtime.

A runtime can often supply their own async version of common functionnality like
sleep, file operation or network IO

## The state machine

In asynchronous programming each `await` keyword is a place where the control is
handed back to the runtime so that it can do other operations while waiting.

To make that work Rust need to keep track of the current state of our async
block

To do that there is an invisible state machine for our block. The state machine
would be like an enum that save the current state at each `await` point

```rust
enum RequestCallFuture<'a> {
    Initial {},
    GetAwaitPoint{},
}
```

This exemple is simple but with more `await` keyword there could be more state
in the enum each representing a where our operation is

We could write our state machine but that would be tedious and we could
introduce bugs, error. Fortunately we don't have to do that and the rust
compiler do it itself


## Stream

