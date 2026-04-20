# Simple PyPI Publishing

A GitHub workflow to manually publish LiteLLM packages to PyPI with a specified version.

## How to Use

1. Go to the **Actions** tab in the GitHub repository
2. Select **Simple PyPI Publish** from the workflow list
3. Click **Run workflow**
4. Enter the version to publish (e.g., `1.74.10`)

## What the Workflow Does

1. **Updates** the version in `pyproject.toml`
2. **Copies** the model prices backup file
3. **Builds** the Python package
4. **Publishes** to PyPI

## Prerequisites

Make sure the following secret is configured in the repository:
- `PYPI_PUBLISH_PASSWORD`: PyPI API token for authentication

## Example Usage

- Version: `1.74.11` → Publishes as v1.74.11
- Version: `1.74.10-hotfix1` → Publishes as v1.74.10-hotfix1

## Features

- ✅ Manual trigger with version input
- ✅ Automatic version updates in `pyproject.toml`
- ✅ Repository safety check (only runs on official repo)
- ✅ Clean package building and publishing
- ✅ Success confirmation with PyPI package link

---

# Build Docker image ignoring test status

If you need a Docker image **right now** even when tests are failing, use:

- Workflow: **Build Image (sin bloquear por tests)**
- File: `.github/workflows/build-image-ignore-tests.yml`

## How to run it

1. Go to **Actions**.
2. Select **Build Image (sin bloquear por tests)**.
3. Click **Run workflow**.
4. Optional inputs:
   - `image_tag`: custom tag like `rc-2026-04-20`.
   - `push_image`: set `true` to push to GHCR, `false` to build only.

## Notes

- This workflow is `workflow_dispatch` only (manual).
- It does **not** depend on test workflows.
- It can build from the selected branch/commit even if other CI checks are red.
