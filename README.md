# Singularity: The Language Base

**Singularity** is an innovative programming language designed for clarity, expressiveness, and the precise articulation of sequential and conditional logic. Leveraging a unique **vector-based syntax** and **JSON-driven parameters**, Singularity empowers developers to define complex workflows, automate intricate processes, and build reactive systems with unparalleled readability and conciseness.

## Table of Contents

1.  [Introduction](#1-introduction)
2.  [Design Philosophy](#2-design-philosophy)
3.  [Key Features](#3-key-features)
4.  [Basic Concepts](#4-basic-concepts)
    * [Function Vectors](#function-vectors)
    * [Function Calls with Parameters](#function-calls-with-parameters)
    * [Nested Function Vectors](#nested-function-vectors)
    * [Data Types (Conceptual)](#data-types-conceptual)
5.  [Core Language Constructs & Examples](#5-core-language-constructs--examples)
    * [Sequential Execution](#sequential-execution)
    * [Conditional Logic (If/Else)](#conditional-logic-ifelse)
    * [Loops (Conceptual)](#loops-conceptual)
    * [Working with Data Structures](#working-with-data-structures)
        * [Lists (Arrays)](#lists-arrays)
        * [Maps (Objects)](#maps-objects)
    * [Function Composition & Reusability](#function-composition--reusability)
    * [Error Handling (Conceptual)](#error-handling-conceptual)
    * [Interacting with External Systems (Conceptual)](#interacting-with-external-systems-conceptual)
6.  [Transpilation to JavaScript](#6-transpilation-to-javascript)
7.  [Getting Started (Conceptual)](#7-getting-started-conceptual)
8.  [Contributing](#8-contributing)
9.  [License](#9-license)

---

## 1. Introduction

In a world increasingly driven by automation and intricate processes, Singularity emerges as a powerful tool to describe and orchestrate operations. It moves beyond traditional imperative paradigms by focusing on the "what" rather than the "how," allowing developers to build robust and maintainable systems that directly mirror business logic or desired behavioral sequences. Its JavaScript transpilation target ensures seamless integration into modern web and server-side applications.

## 2. Design Philosophy

Singularity is built upon several core design principles:

* **Readability as a Priority:** Code should be as close to natural language as possible, making it easy to understand even for those less familiar with programming.
* **Vector-First Approach:** Operations are inherently sequential and grouped, simplifying the mental model of execution flow.
* **Data-Driven Actions:** The use of JSON for parameters encourages explicit data passing and clear separation of concerns.
* **Minimal Syntax Overhead:** Focus on expressing logic directly, reducing boilerplate and cognitive load.
* **Transpiler-Friendly:** Designed from the ground up to generate efficient and idiomatic JavaScript, ensuring broad compatibility and performance.

## 3. Key Features

* **Function Vectors:** Define ordered sequences of operations as simple, declarative lists of functions.
* **JSON-based Parameters:** Pass rich, structured data to functions using familiar JSON objects, enhancing readability and flexibility.
* **Declarative & Human-Readable Syntax:** Emphasizes an intuitive syntax that directly expresses intent, making code easy to understand at a glance.
* **Nested Structures:** Compose complex logic by embedding function vectors and data structures within one another.
* **Control Flow Abstractions:** Built-in constructs for conditional execution and iterative processing.
* **JavaScript Transpilation:** Singularity programs are compiled into standard JavaScript, enabling execution in any modern JavaScript environment (browsers, Node.js, serverless functions, etc.).

## 4. Basic Concepts

### Function Vectors

The fundamental building block in Singularity is the **function vector**, represented by square brackets `[]`. It defines an ordered list of operations, which are executed sequentially from left to right.

```singularity
// A simple function vector executing three functions in order
[initializeSystem, loadConfiguration, startApplication]
```

// Basic Function Vector
[func1, func2, func3]

// Function Call with Parameters
[functionWithParams{param1: "value", param2: 123}, anotherFunction]

// Nested Function Vectors
[
    doSomething,
    [
        subTaskA,
        subTaskB{option: true}
    ],
    finishUp
]

// Example 1: Daily Routine Automation
[
    WhenIWakeUpMakeTeaWith{type: "black", sugar: 2, milk: "none"},
    ThenGoToWork,
    WhenItsLunchTimeEat{meal: "salad", restaurant: "local_deli"},
    ReturnHome,
    PrepareDinner{cuisine: "italian", main_ingredient: "pasta"},
    GoToSleep
]

// Example 2: Conditional Logic
[
    IfTimeIs{now: "09:00"}, callMom,
    IfTimeIs{now: "17:00"}, [sendDailyReport, shutdownComputer]
]

// Example 3: Defining and Calling Custom Functions (Conceptual)
// The actual syntax for defining such functions within Singularity
// is part of future language design.
[
    greet{name: "Alice", timeOfDay: "morning"},
    greet{name: "Bob", timeOfDay: "evening"}
]

// --- Conceptual JavaScript Transpilation Example ---
// Singularity: [WhenIWakeUpMakeTeaWith{type: "black", sugar: 2, milk: "none"}, ThenGoToWork]
// Transpiles to JavaScript:
async function runSequence() {
    await WhenIWakeUpMakeTeaWith({ type: "black", sugar: 2, milk: "none" });
    await ThenGoToWork();
}
// runSequence(); // Would be called to execute

// --- Conceptual Transpiler Usage Command ---
// singularity transpile my_program.sg -o my_program.js

// --- Conceptual Execution Command ---
// node my_program.js
