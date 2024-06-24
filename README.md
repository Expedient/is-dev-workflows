# IS Dev Workflows

This repository contains a set of standardized, reusable GitHub Actions workflows designed to streamline the CI/CD processes for the IS Dev team. These workflows cover various aspects of the development lifecycle, including building and pushing Docker images, running tests, deploying to Kubernetes, and sending notifications.

## Available Workflows

1. **sync-postman-collection.yml**: Synchronizes Postman collections with a specified workspace.
2. **newman-k8s-contract-tests.yml**: Runs contract tests for Kubernetes deployments.
3. **kustomize-deploy-commit.yml**: Updates and commits Kubernetes manifests using Kustomize.
4. **docker-build-and-push.yml**: Builds and pushes Docker images to a registry.
5. **slack-notify.yml**: Sends notifications to Slack about workflow status.
6. **newman-k8s-tests.yml**: Runs functional tests for Kubernetes deployments.
7. **golangci-lint.yml**: Performs linting for Go projects.

## Usage

To use these workflows in your project, reference them in your GitHub Actions workflow file using the `uses` keyword. For example:

```yaml
jobs:
  build:
    uses: expedient/is-dev-workflows/.github/workflows/docker-build-and-push.yml@v1.0.0
    with:
      tags: myapp:latest
    secrets:
      IS_DOCKER_HUB_USERNAME: ${{ secrets.IS_DOCKER_HUB_USERNAME }}
      IS_DOCKER_HUB_PASSWORD: ${{ secrets.IS_DOCKER_HUB_PASSWORD }}
```

Refer to each workflow file for specific input parameters and required secrets.

## Contributing

To contribute to this repository, please follow these steps:

1. Fork the repository
2. Create a new branch for your feature or bug fix
3. Make your changes and commit them
4. Push your changes to your fork
5. Submit a pull request
