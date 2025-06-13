# Singularity: The Language Base

Singularity is a programming language designed to express sequences of operations and complex logic in a concise, vector-based syntax. It focuses on clarity and direct representation of actions, making it ideal for defining workflows, automating tasks, and creating reactive systems.

## Key Features

* **Function Vectors:** Define sequences of operations as ordered lists of functions.
* **JSON-based Parameters:** Pass complex, structured data to functions using familiar JSON objects.
* **Human-Readable Syntax:** Aims for a syntax that is intuitive and easy to understand at a glance.
* **JavaScript Transpilation:** Programs written in Singularity are transpiled into standard JavaScript, allowing for broad compatibility and execution in any JavaScript environment (browsers, Node.js, etc.).

## Basic Concepts

### Function Vectors

In Singularity, programs are primarily composed of **function vectors**, represented by square brackets `[]`. Each element within a function vector is a function call.

```singularity
[func1, func2, func3]


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
