# Changelog

## [Unreleased]

## [v1]
### Added
- Added basic taint propagation system.
- Added the following security extensions to the base library:
  - `forceinsecure()`
  - `geterrorhandler()`
  - `hooksecurefunc([table,] "name", func)`
  - `issecure()`
  - `issecurevariable([table,] "variable")`
  - `scrub(...)`
  - `seterrorhandler(errfunc)`
- Added the following security extensions to the debug library:
  - `debug.forcesecure()`
- Added a new hook mask (`"s"`) which is invoked whenever the VM transitions between security states. This occurs after processing of the current instruction.
- Added a debug trap system that allows configuring errors under certain runtime conditions.
  - This can be controlled through the `debug.settrapmask("mask")` and `debug.gettrapmask()` functions.
  - The `"s"` mask enables integer overflow errors in `string.format` falls for signed format specifiers.
  - The `"u"` mask enables integer overflow errors in `string.format` calls for unsigned format specifiers.
  - The `"z"` mask enables divide-by-zero errors for division and modulo operations.
  - The default trap mask matches that of a live retail client environment and is set to `"s"`.
- Added all string library extensions present in the in-game environment as well as their global aliases.
- Added all table library extensions present in the in-game environment as well as their global aliases.
- Added all math library extensions present in the in-game environment as well as their global aliases.
- Added all global aliases to the OS libary functions as present in the in-game environment.

[Unreleased]: https://github.com/Meorawr/tainted-lua/compare/v1...HEAD
[v1]: https://github.com/Meorawr/tainted-lua/releases/tag/v1