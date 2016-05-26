# Introduction

The purpose of this guide is to teach you how to write a high-quality definition file.
This guide is structured by showing an example *usage* and explaining how to write the corresponding declaration.

## A Word on Approach

The best way to write a definition file is by reading the documentation for the underlying library.
This will allow you to write better names for types and variables, and avoid accidently documenting non-public API surface.

# Definition Files By Example

In each example, we'll begin with either example prose from the documentation, or a code sample of a valid call.

> Prose from the documentation will be formatted like this

and

> `example.code("will be formatted", "like this");`

```ts
// Definition file code will be formatted like this
```

## Global variable

> The global variable `foo` contains the number of widgets present

```ts
/** The number of widgets present */
declare var foo: number;
```

## Global function

> `greet('hello, world');`

```ts
declare function greet(greeting: string): void;
```

## Object with properties

> `var result = myLib.makeGreeting('hello, world');`
> `console.log('The computed greeting is:' + result);`
> `var count = myLib.numberOfGreetings;`

```ts
declare namespace myLib {
    function makeGreeting(s: string): string;	
    let numberOfGreetings: number;
}
```

## Overloaded function

> The `getWidget` function accepts a number and return a Widget, or accepts a string and returns a Widget array

```ts
declare function getWidget(n: number): Widget;
declare function getWidget(s: string): Widget[];
```
