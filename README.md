# [tus](https://tus.io) Protocol Conformance Test Suite

A comprehensive test suite for validating tus resumable upload protocol v1.0.0 server implementations.

- **[Specification](https://github.com/tus/tus-resumable-upload-protocol/blob/83541f361872002bb26a3571bff71b10408ef91f/protocol.md)** (as of 2016-03-25) (also available on the [website](https://tus.io/protocols/resumable-upload.html))
- [OpenAPI](https://github.com/tus/tus-resumable-upload-protocol/blob/83541f361872002bb26a3571bff71b10408ef91f/OpenAPI/openapi3.yaml)

## Overview

The [test suite](tests/) includes:

- **Core Protocol Tests** - Required for all implementations (27 tests)
- **Extension Tests** - Modular tests for each tus extension (52 tests)
- **Scenario Tests** - End-to-end workflow validation (13 tests)
- **Optional Tests** - Behavioral tests for undefined spec areas (31 tests)

**Total: 123 tests**

## Requirements

### The easy way

- [Dagger](https://dagger.io) using beta release `86d1d2f5791bcf3213d56903cfa81a3ba0abe54a`

### The hard way

- [hurl](https://hurl.dev/) v7.1.0 or later
- A running tus server implementation to test against
- Docker and Docker Compose (optional, for running test servers)

> [!TIP]
> [devenv](https://devenv.sh) and [mise](https://mise.jdx.dev) configure the required Dagger beta release. Otherwise, set `DAGGER_X_RELEASE=86d1d2f5791bcf3213d56903cfa81a3ba0abe54a` before running Dagger.

## Quick Start

1. **Run all tests**
   ```bash
   dagger call tests run sync
   ```

2. **Export HTML report**
   ```bash
   dagger call tests run --report HTML export --path results
   ```

## References

### Protocol & Tools
- [tus Protocol v1.0.0](https://tus.io/protocols/resumable-upload)
- [hurl Documentation](https://hurl.dev/docs)

### tus Server Implementations
- [tusd](https://github.com/tus/tusd) - Official reference implementation (Go)
- [rustus](https://github.com/s3rius/rustus) - High-performance Rust implementation
- [tus-node-server](https://github.com/tus/tus-node-server) - Official Node.js implementation
- [tus Implementations List](https://tus.io/implementations) - Complete list of tus implementations

## License

The project is licensed under the [MIT License](LICENSE).
