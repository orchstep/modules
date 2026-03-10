# OrchStep Module Registry

Official module registry for [OrchStep](https://github.com/orchstep/orchstep) — reusable workflow automation modules.

## Available Modules

| Module | Description | Version |
|--------|-------------|---------|
| `demo-slack-notify` | Send notifications to Slack (mock for demo) | v1.0.0 |
| `demo-health-check` | HTTP endpoint health verification | v1.0.0 |
| `demo-git-release` | Git tagging and release notes generation | v1.0.0 |
| `demo-report-gen` | Generate reports in multiple formats | v1.0.0 |
| `demo-env-check` | Verify development environment prerequisites | v1.0.0 |

> **Note:** Modules prefixed with `demo-` use mock/simulated backends for educational purposes.
> They demonstrate real orchestration patterns you can adapt with real API endpoints.

## Usage

In your `orchstep.yml`:

```yaml
modules:
  - name: slack
    source: github.com/orchstep/modules
    version: "^1.0.0"
    path: modules/demo-slack-notify
    config:
      channel: "#deployments"
      webhook_url: "https://hooks.slack.com/your/webhook"
```

Or using `@orchstep` scope shorthand:

```yaml
modules:
  - name: slack
    source: "@orchstep/demo-slack-notify"
    version: "^1.0.0"
    config:
      channel: "#deployments"
```

## Module Structure

Each module contains:
- `orchstep.yml` — Workflow tasks (the actual logic)
- `orchstep-module.yml` — Metadata, config schema, exports
- `README.md` — Usage documentation

## Contributing

1. Create a new directory under `modules/`
2. Add `orchstep.yml` and `orchstep-module.yml`
3. Tag with `module-name/vX.Y.Z` format
