# Workflow Templates

This repository contains reusable GitHub Actions workflow templates for various development and deployment processes. The current workflow template automates the process of creating a release for a plugin project.

## Available Workflow Templates

### 1. Create Release Workflow

Automates the process of creating a release for a plugin. It includes steps to:
- Set up PHP and Node.js environments.
- Install NPM and Composer dependencies.
- Package the plugin as a ZIP file.
- Create a new GitHub release and upload the ZIP file.

#### Workflow Template Path
`.github/workflow-templates/create-release.yml`

#### Usage

To use this workflow template in your repository:

1. Add the `create-release.yml` workflow template to your repository by following the [GitHub documentation](https://docs.github.com/en/actions/learn-github-actions/sharing-workflows-with-your-organization).
2. Trigger the workflow manually through the "Actions" tab in your repository.

#### Workflow Inputs

| Input Name   | Description                                           | Required | Default |
|--------------|-------------------------------------------------------|----------|---------|
| `version`    | Version name for the release (e.g., `1.0.0`)          | Yes      | `1.0.0` |
| `plugin_name`| Name of the plugin to be released                     | Yes      |         |

#### Secrets

Make sure the following secret is available in your repository:
- `PAT_TOKEN`: Personal access token with the `repo` scope to create releases and upload assets.

#### Example Workflow Dispatch

When triggering the workflow manually, provide the following inputs:
- **Version:** The version for the release, e.g., `2.1.0`.
- **Plugin Name:** The name of your plugin, e.g., `my-awesome-plugin`.