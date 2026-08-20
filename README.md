# `@kawaikara/site-api`

Public TypeScript contract for authoring Kawaikara `.kawai` Bundles, Providers,
Plugins, settings, shortcuts, browser profiles, short-form controls, and
sandboxed PluginView panels.

## Install

The package is distributed as an immutable tarball attached to this
repository's GitHub Releases:

```json
{
  "devDependencies": {
    "@kawaikara/site-api": "https://github.com/Kawaikara/kawai-site-api/releases/download/v1.0.0/kawaikara-site-api-1.0.0.tgz"
  }
}
```

The API release version and a Bundle manifest's numeric `apiVersion` are
different compatibility layers. Kawaikara currently supports manifest
`apiVersion: 1`.

## PluginView identity and security

Provider panels are declared in `menu.panels`; Plugin panels are declared in
`@plugin({ panels })`. A visible title may be duplicated. Kawaikara selects a
panel using the stable owner id plus the locally scoped panel id.

HTML panels run in a sandboxed document without Kawaikara IPC or access to the
overlay Renderer. App-owned panels use the `internal` content kind.

## Development

```bash
npm ci
npm run typecheck
npm run build
```

Source snapshots are maintained from Kawaikara's `packages/site-api` subtree.
Tagged releases are published only from this dedicated repository.
