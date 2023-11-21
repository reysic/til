# Installing On macOS

Though macOS includes Python 3 (`which python3` will yield `/usr/bin/python3`), install Homebrew's version for more frequent updates:

```bash
brew install python3
```

Add aliases for ohmyzsh to avoid need to edit system defaults:

```bash
nano $ZSH_CUSTOM/aliases.zsh
```

```text
alias python3=/opt/homebrew/bin/python3
```

## References

- [StackExchange](https://apple.stackexchange.com/a/461063)
- [Homebrew](https://docs.brew.sh/Homebrew-and-Python)
