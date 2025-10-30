# Contributing to bayes-stat-modeling

Thank you for your interest in contributing to this repository! This guide will help you get started.

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion for improvement:

1. Check if the issue already exists in the [Issues](../../issues) section
2. If not, create a new issue with a clear title and description
3. Include relevant details such as:
   - Steps to reproduce (for bugs)
   - Expected vs. actual behavior
   - Your environment (OS, R/Python version, etc.)

### Submitting Changes

1. **Fork the repository** and create a new branch for your changes
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes** following the project structure:
   - Place new models in the `models/` directory
   - Follow the template structure in `templates/bayesian-analysis.qmd`
   - Update documentation as needed

3. **Test your changes** in the dev container environment
   - Ensure all models compile and run successfully
   - Verify Quarto documents render correctly

4. **Commit your changes** with clear, descriptive messages
   ```bash
   git commit -m "Add: description of your changes"
   ```

5. **Push to your fork** and submit a pull request
   ```bash
   git push origin feature/your-feature-name
   ```

## Development Environment

This repository uses a Docker dev container with all necessary dependencies. To get started:

1. Install [Docker](https://www.docker.com/) and [VS Code](https://code.visualstudio.com/)
2. Install the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
3. Open the repository in VS Code
4. Click "Reopen in Container" when prompted

## Code Style Guidelines

### R Code
- Use 2 spaces for indentation
- Follow [tidyverse style guide](https://style.tidyverse.org/)
- Use meaningful variable names

### Python Code
- Use 4 spaces for indentation
- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/)
- Use type hints where appropriate

### Stan Code
- Use 2 spaces for indentation
- Add comments to explain model structure
- Follow [Stan style guide](https://mc-stan.org/docs/stan-users-guide/style-guide.html)

### Quarto Documents
- Follow the template structure in `templates/`
- Include data dictionary for all analyses
- Add appropriate references
- Use code folding for long code blocks

## Model Workflow

When adding a new model, follow the Bayesian workflow proposed by Gelman et al. (2020):

1. Create a new folder in `models/` with a descriptive name
2. Include the following files:
   - `model.stan` - Stan model code
   - `{model-name}.qmd` - Analysis document
   - `data-dictionary.csv` - Variable descriptions
3. Document the model in the main README.md table
4. Follow the analysis structure:
   - Context and goals
   - Data description and EDA
   - Model formula and implementation
   - Results interpretation
   - References

## Questions?

If you have questions about contributing, feel free to:
- Open an issue with the "question" label
- Reach out to the maintainers

Thank you for contributing to this project!
