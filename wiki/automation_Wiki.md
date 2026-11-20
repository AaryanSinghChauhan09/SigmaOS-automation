# SigmaOS-automation Component Wiki

## Overview
SigmaOS-automation provides automation component for the SigmaOS operating system. It demonstrates the automation framework and rule-based execution within the SigmaOS ecosystem, following the principles of clear abstraction and deterministic task initialization.

## Principles
- Single Responsibility
- Automation Framework
- Fail-Fast on Automation Errors
- Deterministic Task Initialization
- Clear Abstraction Over Automation APIs
- Composition over Inheritance for task rule extensions

## Architecture
SigmaOS-automation follows an automation framework pattern:
- **Framework Core**: Provides task execution, rule evaluation, and hook primitives
- **Rule Definitions**: Supports rule definitions, conditions, and action triggers
- **Execution Management**: Manages task execution, state, and lifecycle
- **Hook Integration**: Integrates with system hooks and lifecycle events

## API
The component provides the following public APIs:
- `framework::execute(task)` - Execute a task
- `framework::rule::eval(rule, context)` - Evaluate a rule against a context
- `framework::hook::trigger(name)` - Trigger a lifecycle hook
- `framework::status()` - Get framework status and active tasks
- Error types for automation errors or invalid rule configurations

## Test Structure (Arrange-Act-ASSERT)
All tests follow the AAA pattern:
1. **Arrange**: Set up test environment with specific automation configuration
2. **Act**: Execute the code under test (task execution, rule evaluation)
3. **Assert**: Verify the expected automation results

Example:
```rust
#[test]
fn test_framework_execute_aaa() {
    // Arrange
    let task = "system_check";
    
    // Act
    let result = framework::execute(task);
    
    // Assert
    assert!(result.is_ok());
    assert!(framework::status().is_task_active("system_check"));
}
```

## Development
- Follows Rust best practices with `#![forbid(unsafe_code)]`
- Automation initialization is best-effort; gracefully degrades on unsupported configurations
- Comprehensive error types for all automation failure scenarios
- Unit tests provided for task execution, rule evaluation, and hook integration
- Integration tests for full automation framework with system hooks and lifecycle events

## TODO
- Add support for additional task types and execution criteria
- Expand rule management capabilities (complex conditions, priority)
- Add execution management (state, lifecycle, dependencies)
- Create integration tests with actual system hooks and lifecycle events
- Implement task priority and dependency management