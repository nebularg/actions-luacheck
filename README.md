# actions-luacheck

## Usage

```yaml
- uses: nebularg/actions-luacheck@v1
  with:
    # A list of files, rockspecs, or directories to be checked.
    # Filenames will display relative to the workspace directory.
    # Default: ${{ github.workspace }}
    files: ''

    # Additional command-line arguments.
    # See https://luacheck.readthedocs.io/en/stable/cli.html
    args: ''

    # URL to a custom configuration (`.luacheckrc`) file that will be
    # used as the default config.
    config: ''
```

## Examples

### Lint only

```yaml
- uses: nebularg/actions-luacheck@v1
  with:
    args: -o 011
```

### Use one .luacheckrc for multiple projects

```yaml
- uses: nebularg/actions-luacheck@v1
  with:
    config: https://gist.githubusercontent.com/nebularg/aaccb396168a4076a7a0b7dbcbe6fb42/raw/36a15bd6b375351321711bb21095091ab90087b9/.luacheckrc
```

### Only run on specific files

```yaml
- uses: nebularg/actions-luacheck@v1
  with:
    files: Core.lua Modules/
    args: -qo 011
```
