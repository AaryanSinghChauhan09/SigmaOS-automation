# SigmaOS Automation

This crate exports `AutomationEngine` and groups APIs for scripts, hotkeys,
macros, scheduling, and orchestration. The module tree does not establish that
arbitrary scripts or system actions are safely executed. Review each action
path for argument handling, permissions, cancellation, and audit behavior
before connecting it to user input or a privileged service.

## License

See [`LICENSE`](LICENSE) and [`Cargo.toml`](Cargo.toml).

