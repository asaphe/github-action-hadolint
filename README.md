# github-action-hadolint

A composite GitHub Action that downloads and runs Hadolint (Dockerfile linter) without requiring Docker or container actions. Includes a problem matcher for inline PR annotations.

## Usage

```yaml
- uses: asaphe/github-action-hadolint@v1
  with:
    dockerfile: Dockerfile
```

### With Custom Config

```yaml
- uses: asaphe/github-action-hadolint@v1
  with:
    dockerfile: docker/Dockerfile.production
    config: .hadolint.yaml
```

## Inputs

| Name | Description | Required | Default |
|------|-------------|----------|---------|
| `dockerfile` | Path to the Dockerfile to lint | Yes | - |
| `config` | Path to Hadolint configuration file | No | - |

## Features

- Downloads Hadolint v2.12.0 binary (no Docker required)
- Platform-aware (Linux x86_64 and ARM64)
- GitHub problem matcher for inline annotations on PRs
- Exports `HADOLINT_RESULTS` env var for downstream steps
- Works on self-hosted runners without Docker

## License

Apache 2.0 - See [LICENSE](LICENSE) for details.
