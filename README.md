# actions-luacheck

## Usage

```yaml
- uses: nebularg/actions-luacheck@v1
  with:
    # A list of files, rockspecs, or directories to be checked. Paths can be
    # absolute or relative to the `path` option.
    files: ''

    # The working directory for luacheck. The file list should be relative to
    # this path and output filenames be displayed relative to this path.
    # Default: ${{ github.workspace }}
    path: ''

    # Additional command-line arguments.
    # See https://luacheck.readthedocs.io/en/stable/cli.html
    args: ''

    # URL to a custom configuration (`.luacheckrc`) file that will be used as
    # the default configuration file.
    config: ''

    # Emits annotations for source code at locations parsed from the output.
    # Must be set to "none", "warning" or "error".
    #
    # Requires that output of warnings not be suppressed through the -qq or -qqq arguments.
    #
    # Default: 'none'
    annotate: 'none'
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
