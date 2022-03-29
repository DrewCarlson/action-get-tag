# Get tag or empty string Github Action

Simple Action that have only one responsibility - output tag name (parsed from `GITHUB_REF` environment variable) or an empty string.

## Usage

Should be used only when actual tag is pushed, otherwise the Action will have no output.

```yaml
on:
  push:
    tags:
      - '*'
```

```yaml
- name: Get tag
  id: tag
  uses: DrewCarlson/action-get-tag@v1
  with:
    # Optionally strip `v` prefix
    strip_v: true
- name: Use tag
  run: echo ${{steps.tag.outputs.tag}}
```
