# Cognitive Load Optimization: Best Practices for AI Code Generation

*This ruleset extends our existing guidelines on clean code, DRY principles, and other software engineering best practices. It focuses specifically on optimizing for human cognitive limitations.*

## Core Principle

All code should be optimized for the fundamental constraint of human cognition: working memory can only hold approximately 4 chunks of information simultaneously. When this threshold is exceeded, comprehension deteriorates rapidly.

## Guidelines for Minimizing Cognitive Load

### 1. Prioritize Mental Model Simplicity
- **Rule CL-1:** Generate code that follows predictable patterns and requires minimal mental context-switching.
- **Rule CL-2:** Favor explicit code over implicit behavior, even at the cost of verbosity.
- **Implementation:** When multiple approaches exist, choose the one requiring the fewest mental transformations to understand, not necessarily the most elegant or concise.

### 2. Optimize Conditional Logic
- **Rule CL-3:** Extract complex boolean expressions into well-named variables that describe their purpose.
- **Rule CL-4:** Structure functions with early returns for invalid states rather than deep nesting.
- **Implementation:** A human should be able to track the execution path without maintaining a mental stack of conditions.

### 3. Balance Information Hiding and Locality
- **Rule CL-5:** Favor "deep modules" with simple interfaces over many "shallow modules" with complex interactions.
- **Rule CL-6:** Keep related code physically close together when possible.
- **Implementation:** Apply DRY principles judiciously - duplicate small amounts of code when the alternative would require context-switching across multiple files or components.

### 4. Minimize Required Background Knowledge
- **Rule CL-7:** Use self-describing data (strings over numeric codes) for error handling, status codes, and enumerations.
- **Rule CL-8:** When using language features, prefer common patterns over obscure optimizations.
- **Implementation:** Code should be understandable without requiring extensive domain-specific knowledge or memorization of arbitrary mappings.

### 5. Apply Abstraction Strategically
- **Rule CL-9:** Introduce abstraction layers only when they meaningfully reduce overall system complexity.
- **Rule CL-10:** When creating APIs, optimize for usage simplicity over implementation simplicity.
- **Implementation:** Every layer of indirection incurs a cognitive cost; ensure this cost is justified by greater benefits.

### 6. Support Linear Reading and Understanding
- **Rule CL-11:** Structure code to enable top-to-bottom reading where possible.
- **Rule CL-12:** Use guard clauses and fail-fast approaches to keep the main logic path clear.
- **Implementation:** A developer should be able to understand code by reading it linearly, without needing to jump between multiple locations.

## Decision Making Framework

When faced with multiple implementation options, apply the following questions in order:

1. Which approach requires the least working memory to understand?
2. Which approach minimizes the need to reference other parts of the codebase?
3. Which approach would be most comprehensible to a new team member?
4. Which approach separates intrinsic complexity (necessary to solve the problem) from extraneous complexity (artifacts of the implementation)?

Remember: Optimize for human comprehension first, then for other considerations like performance or theoretical elegance. The most elegant solution is the one that places the least burden on human working memory.
