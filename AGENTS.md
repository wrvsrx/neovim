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
StyLua. Set `VIMRUNTIME` manually when running Neovim or its tests, for example:

```sh
VIMRUNTIME="$PWD/runtime" nix develop -c make functionaltest \
  TEST_FILE=test/functional/plugin/lsp/folding_range_spec.lua
```

When working on a branch that does not contain `flake.nix`, obtain the latest
development environment from a branch that does, for example:

```sh
nix develop 'git+file:///home/wrvsrx/Documents/neovim?ref=refs/heads/patched-0.12.5' -c cmake --version
```

Prefer these commands when the host environment does not provide the required
Neovim build tools.

## AI Disclosure

If AI was used in any way for a commit, add an `AI-assisted: <tool name>` trailer to the commit message.
If the user commits manually, remind them to add it.
