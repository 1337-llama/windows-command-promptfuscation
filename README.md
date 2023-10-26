<p align="center">
  <img src="https://github.com/1337-llama/windows-command-promptfuscation/assets/71475034/03266907-840a-4904-bdd5-3d088c170645">
</p>

# Windows Command Promptfuscation (WCP)

A tool designed for obfuscating Command Prompt inputs. 

*But what's Command Prompt?* you might ask yourself. It's also referred to as `cmd.exe` - the really old school command window used in Windows.

![image](https://github.com/1337-llama/windows-command-promptfuscation/assets/71475034/bd57b45c-2706-4c04-bc2e-17702ccc4142)

There's a lot of tools both here on GitHub and in other places that can be used to obfuscate PowerShell and Linux shell (`bash`, `fish`, `zsh`, `sh`, etc.) commands. But our poor friend Command Prompt is often left out in the cold 🥶. Alas, this project aims to remedy this issue.

## First Things First

Before attempting to obfuscate a command, **PLEASE** ensure that it actually works *first*. You may try over and over again to get an obfuscated command to function properly, only to realize that `ipcongif` won't work either 😁.

**ALSO**, Command Prompt is a non-deterministic wonder of computing. Any command run through WCP is potentially subject to not working, so you'll hear me rant throughout this README - **make sure to test all outputs before assuming they work!**

## Best Practices

- Use forward slashes (`/`) for paths. Don't use backslashes (`\`). Some transform types (I'm looking at you, forcoding...) can accept backslashes. Others (like payload encoding) cannot.

## Tips and Tricks

- **IMPORTANT**: If you keep testing your commands and they keep failing - try restarting `cmd.exe`. Why? The world may never know. But a simple restart can easily correct a number of problems.
- If you surround a piece of your command in `~` characters, it won't be modified. For instance, `whoami ~/all~` won't obfuscate the `/all` text.
  - Some transforms might not be able to support this, so be vigilant and **check your commands before running them in production!**
- Outputs that rely upon the `g` (global alphabet) operation can be a bit more fragile than other operations. Again, **check your outputs!**

# Operations

WCP has a few different operations that can be employed.

- `c`
- `t`
- `a`
- `g`

## Resources

A white paper titled *DOSfuscation: Exploring the Depths of Cmd.exe Obfuscation and Detection Techniques* by Daniel Bohannon of FireEye was relied upon heavily for this project 🔬.
