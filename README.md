# deadnix-action

Automatically creates pull requests to remove unused code in `.nix`
files

## Usage

Create a `.github/workflows/deadnix.yml` file:

```yaml
on: [push]

name: Dead code analysis

jobs:
  deadnix:
    name: Deadnix
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: cachix/install-nix-action@v30
      - uses: cachix/cachix-action@v15
        with:
          name: deadnix
      - uses: astro/deadnix-action@main
```

`git add`, `git commit`, `git push`, be happy.
