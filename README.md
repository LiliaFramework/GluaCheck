<p align="center">
 <strong>GLuaCheck — Lilia-Oriented Lua & GLua Static Analysis</strong><br/>
 A Lilia-maintained Luacheck-based code-quality tool for detecting common Lua and GLua issues before they reach production.<br/>
 Use it to catch undefined globals, unused variables, unreachable code, uninitialized values, and other configurable warnings.
</p>

<p align="center">
 <img src="https://github.com/LiliaFramework/Lilia/blob/main/logo.png?raw=true" alt="Lilia Logo" width="220" />
</p>

<p align="center">
 <a href="./LICENSE">
  <img src="https://img.shields.io/badge/License-MIT-brightgreen.svg" alt="MIT License" />
 </a>
 <img src="https://img.shields.io/badge/Lua-Static%20Analysis-2C2D72?logo=lua&logoColor=white" alt="Lua Static Analysis" />
 <a href="https://liliaframework.github.io">
  <img src="https://img.shields.io/badge/Ecosystem-Lilia-blue" alt="Lilia" />
 </a>
</p>

---

## Overview

GLuaCheck is the Lilia ecosystem's Luacheck-based static-analysis repository.

Luacheck detects issues such as:

- Undefined global variables
- Unused variables and values
- Uninitialized variables
- Unreachable code
- Suspicious assignments
- Non-standard globals
- Configurable warning classes

The analyzer supports Lua 5.1, Lua 5.2, Lua 5.3, and LuaJIT syntax through the underlying Luacheck codebase.

## Basic Usage

After a compatible Luacheck installation is available, check files or directories with:

```bash
luacheck src extra_file.lua another_file.lua
```

A typical result reports warnings and errors with file locations:

```text
Checking src/good_code.lua               OK
Checking src/bad_code.lua                3 warnings

Total: 3 warnings / 0 errors in 2 files
```

Configuration can be supplied through command-line options, config files, or supported inline comments.

## Running from This Repository

For development use, Luacheck can be run directly from the repository source:

```bash
lua -e 'package.path="./src/?.lua;./src/?/init.lua;"..package.path' bin/luacheck.lua <path>
```

Development dependencies may be required depending on the command and test suite being used.

## Lilia Integration

Lilia projects can use GLuaCheck to keep framework, schema, and module code consistent during development and CI workflows.

Project-specific globals and warning behavior can be configured through `.luacheckrc` files.

The main Lilia repository contains an example configuration suitable for its own codebase.

## Development

To work on the analyzer itself, clone the repository and make changes against the source tree.

For the upstream Luacheck development workflow, `luarocks make` can be used to install a development version.

Tests use the existing Luacheck test infrastructure.

## Upstream

GLuaCheck is based on **Luacheck**, originally developed by Peter Melnichenko.

Upstream documentation:

https://luacheck.readthedocs.io/en/stable/

The upstream project provides the underlying analyzer behavior and documentation for the Luacheck command-line interface and configuration system.

## License

This repository retains the MIT License used by Luacheck.

See [LICENSE](./LICENSE) for the complete license text and attribution.