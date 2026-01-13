# Default Branch Migration: master → main

This document outlines the steps needed to update the default branch of the jocawtho/azure-rest-api-specs fork from `master` to `main` and sync it with the upstream Azure/azure-rest-api-specs repository.

## Current Status

- **Upstream repository** (Azure/azure-rest-api-specs): Uses `main` as the default branch ✓
- **Fork repository** (jocawtho/azure-rest-api-specs): Currently uses `master` as the default branch ✗
- **Local workspace**: Already on `main` branch, synced with upstream/main ✓

## Required Actions

### 1. Change Default Branch on GitHub (Manual Step Required)

Since changing the default branch requires GitHub web interface or API access:

1. Go to https://github.com/jocawtho/azure-rest-api-specs/settings/branches
2. Under "Default branch", click the switch/pencil icon
3. Select `main` from the dropdown
4. Click "Update" and confirm the change

**Note:** If the `main` branch doesn't exist yet on the fork, it will be created when this PR is merged.

### 2. Sync Fork with Upstream

The local `main` branch is already up to date with `upstream/main` (commit: 1864d2ef77).

When this PR is merged, it will:
- Create/update the `main` branch on jocawtho/azure-rest-api-specs
- Ensure it's synced with the latest changes from Azure/azure-rest-api-specs

### 3. Optional: Archive or Delete the Old `master` Branch

After confirming that `main` is set as the default branch and everything is working:

1. Consider renaming the old `master` branch to `legacy-master` or similar for historical reference
2. Or delete it if it's no longer needed

The fork already has a `legacy-master` branch which appears to be an archived version of the old master.

## Technical Details

- **Upstream main** (Azure/azure-rest-api-specs): commit 1864d2ef77
- **Fork master** (jocawtho/azure-rest-api-specs): commit 114a3ad917 (outdated, grafted)
- **Fork main**: Will be created/updated to match upstream when this PR is merged

## Files That Reference "master"

Most references to "master" in the codebase are:
- External repository links (e.g., opencontainers, openai-openapi repositories)
- Example data in API specifications
- Test files

No changes to these files are required as they reference external repositories, not this repository's branches.
