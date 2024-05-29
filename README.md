After upgrading to PNPM v9 `turbo prune` breaks when a workspace includes
injected dependencies

```json
  "dependenciesMeta": {
    "library": {
      "injected": true
    }
  }
```

```
❯ pnpm exec turbo prune --scope application
Generating pruned monorepo for application in /Users/gerbenneven/projects/pnpm-turbo-prune-repro/out
 - Added application
 - Added library
  × No lockfile entry found for 'link:../../../libraries/library'
```

## Repro steps:

Make sure you have pnpm@v9.1.3

1. `$ pnpm install`
2. `$ pnpm exec turbo prune --scope application`
