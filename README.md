# setup-bat

A reusable GitHub Action that installs [`bat`](https://github.com/sharkdp/bat) (`batcat` on Ubuntu) with caching, and adds a wrapper so it always runs with:

```
--plain --paging=never
```

Perfect for automation scripts in CI.

## Usage

```yaml
jobs:
  example:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4
      
      - name: Setup bat
        uses: ohjelmistokehitys/batcat@v1

      - name: Run bat
        run: |
          bat README.md
```