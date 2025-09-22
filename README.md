# setup-bat

A reusable GitHub Action that installs [`bat`](https://github.com/sharkdp/bat) (`batcat` on Ubuntu) with caching, and adds a wrapper so it always runs with:

```
--plain --paging=never
```

Perfect for automation scripts in CI.

## Usage

```yaml
jobs:
  demo:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup bat
        uses: your-org/setup-bat@v1

      - name: Run bat
        run: |
          bat README.md
          bat --line-range 1:10 README.md
```