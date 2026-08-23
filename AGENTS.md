# AGENTS.md

## Development Environment

This fork provides a reproducible development shell through the Nix flake.
Enter it from the repository root with:

```sh
nix develop
```

Commands can also be run without entering an interactive shell:

```sh
nix develop -c cmake --version
nix develop -c make
nix develop -c make functionaltest TEST_FILE=test/functional/plugin/lsp/folding_range_spec.lua
```

The shell provides CMake, a C compiler, GNU Make, Ninja, pkg-config, Git, and
StyLua. It also sets `VIMRUNTIME` to the flake's snapshot of this checkout's
`runtime` directory.
Prefer these commands when the host environment does not provide the required
Neovim build tools.

## AI Disclosure

If AI was used in any way for a commit, add an `AI-assisted: <tool name>` trailer to the commit message.
If the user commits manually, remind them to add it.
