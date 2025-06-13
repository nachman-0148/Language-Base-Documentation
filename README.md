# Singularity: The Language Base

Singularity is a novel programming language designed to express sequences of operations and complex logic in a concise, **vector-based syntax**. It focuses on clarity and direct representation of actions, making it an ideal choice for defining workflows, automating tasks, and building reactive systems.

## Key Features

* **Function Vectors:** Define ordered sequences of operations as simple lists of functions.
* **JSON-based Parameters:** Pass rich, structured data to functions using familiar JSON objects, enhancing readability and flexibility.
* **Declarative & Human-Readable Syntax:** Emphasizes an intuitive syntax that directly expresses intent, making code easy to understand at a glance.
* **JavaScript Transpilation:** Singularity programs are transpiled into standard JavaScript, ensuring broad compatibility and seamless execution in any JavaScript environment (browsers, Node.js, etc.).

## Basic Concepts

### Function Vectors

In Singularity, programs are primarily composed of **function vectors**, represented by square brackets `[]`. Each element within a function vector is a function call, and they are executed in the order they appear.

```singularity
[func1, func2, func3]
