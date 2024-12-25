# Setup Ninja

[GitHub Action](https://github.com/features/actions) for installing Ninja into the `PATH` for the job.

This action downloads the official binaries from the [ninja-build](https://github.com/ninja-build/ninja) repository rather than using a package manager.

Supports Windows, Linux, and macOS.

## Inputs

- `version`: Version of Ninja to install (default: `1.12.1`).
- `platform`: Override platform detection logic.
- `destination`: Target directory for download, added to `PATH` (default: `${GITHUB_WORKSPACE}/ninja-build`).
- `http_proxy`: Optional proxy server hostname.

## Usage Example

```yaml
jobs:
  publish:
    - name: Checkout repository
      uses: actions/checkout@v4

    - name: Setup ninja
      uses: seanmiddleditch/gha-setup-ninja@master

    - run: |
        mkdir build
        cd build
        cmake -G Ninja ..

    - run: cmake --build build
```

## License

MIT License. See [LICENSE](LICENSE) for details.
