# Demo CICD With GitHub Actions

This repository contains a sample YAML file for setting up Continuous Integration and Continuous Deployment (CI/CD) for a Node.js application. The CI/CD workflow is designed to run tests and build the application on different operating systems and Node.js versions.

## Workflow Configuration

The workflow is triggered by pull requests targeting the `main` branch.

### Test Job

The `test` job is responsible for running tests and building the application. It runs on the latest Ubuntu environment (`ubuntu-latest`), and the Node.js version is specified in a matrix strategy, allowing tests to be executed on Node.js versions 12, 14, and 16. The job also runs on macOS (`macos-latest`) and Windows (`windows-latest`) environments for broader coverage.

#### Environment Variable

-   `MODE`: Specifies the environment mode as `dev`.

#### Steps

1. **Checkout code**: Checks out the repository code using the `actions/checkout` action.

2. **Set up Node.js**: Sets up the specified Node.js version using the `actions/setup-node` action.

3. **Install dependencies**: Installs project dependencies using `npm install`.

4. **Run Test**: Executes the test command defined in the project's `package.json` file using `npm test`.

5. **Build**: Runs the build command defined in the project's `package.json` file using `npm run build`.

## Usage

To use this CI/CD configuration in your own project:

1. Create a new repository or navigate to an existing repository where you want to enable CI/CD.

2. Create a new workflow file named `ci-cd.yml` (or any name you prefer) under the `.github/workflows` directory.

3. Copy the contents of the provided YAML file and paste them into your `ci-cd.yml` file.

4. Customize the workflow as needed, such as modifying the test and build commands or adjusting the matrix strategy for different versions.

5. Commit and push the changes to your repository.

6. The CI/CD workflow will be triggered automatically on pull requests targeting the `main` branch, running tests and building the application on different platforms and Node.js versions.

7. Monitor the workflow execution in the Actions tab of your GitHub repository.

That's it! You now have a basic CI/CD setup for your Node.js application using GitHub Actions. Feel free to modify the workflow to suit your specific project requirements.

For more information on configuring and customizing GitHub Actions workflows, refer to the [GitHub Actions documentation](https://docs.github.com/en/actions).
