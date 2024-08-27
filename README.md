# changelog-action

A composite action that wraps the
[git-cliff](https://github.com/orhun/git-cliff)
[action](https://github.com/orhun/git-cliff-action) with a default
config

## Input variables

- `config`: Path of the configuration file. (Default: `"cliff.toml"`)
- `args`: [Arguments](https://github.com/orhun/git-cliff#usage) to pass
  to git-cliff. (Default: `"-v"`)
- `output`: The output file to write to (Default: `"CHANGELOG.md"`)

## Output variables

- `changelog`: Output file that contains the generated changelog.

## Example usage

### Generate the changelog

``` yaml
generate-changelog:
  runs-on: ubuntu-latest
  steps:
  - uses: actions/checkout@v2
    with:
      fetch-depth: 0
      ref: v1.1.0
  - uses: PurpleBooth/changelog-action@v0.3.3
    with:
      args: v1.0.0..v1.1.0
```
