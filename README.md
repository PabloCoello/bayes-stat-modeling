# Bayesian Statistical Modeling

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue.svg)](https://www.docker.com/)
[![Stan](https://img.shields.io/badge/Stan-Statistical%20Modeling-red.svg)](https://mc-stan.org/)
[![Quarto](https://img.shields.io/badge/Quarto-Publishing-orange.svg)](https://quarto.org/)

This repository is dedicated to hosting Bayesian statistical analyses following the Bayesian workflow proposed by Gelman et al. (2020). It includes templates for documenting analyses with best practices, useful references, and a containerized execution environment with validated dependencies for reproducible research.

## Features

- 🐳 **Containerized Environment**: Pre-configured Docker development environment with R, Python, and Stan
- 📊 **Bayesian Workflow**: Structured approach following established best practices
- 📝 **Documentation Templates**: Quarto-based templates for reproducible analysis documentation
- 🔧 **Multi-language Support**: Works with both R and Python implementations
- 📈 **Model Comparison**: Built-in framework for comparing multiple models

## Quick Start

1. **Clone the repository**:
   ```bash
   git clone https://github.com/PabloCoello/bayes-stat-modeling.git
   cd bayes-stat-modeling
   ```

2. **Open in Development Container**:
   - Open the project in VS Code
   - When prompted, click "Reopen in Container" or press `Ctrl+Shift+P` and select "Dev Containers: Reopen in Container"

3. **Start analyzing**:
   - Use the templates in the `templates/` folder to create new analyses
   - Follow the Bayesian workflow outlined below

## Repository Structure

This repository is organized as follows:

```plaintext
bayes-stat-modeling/
├── .devcontainer/              # Docker development environment
│   ├── Dockerfile             # Container configuration
│   ├── devcontainer.json      # VS Code dev container settings  
│   └── requirements/          # Dependencies
│       ├── requirements.txt   # Python packages
│       ├── requirements-src.R # R packages from source
│       └── requirements-bin.txt # Binary dependencies
├── templates/                 # Analysis templates
│   ├── bayesian-analysis.qmd  # Quarto template for analyses
│   ├── bayesian-analysis.html # Rendered template example
│   └── data-dictionary.csv    # Template data dictionary
├── models/                    # Individual model implementations
│   └── eight-schools/         # Example: Eight schools model
│       ├── model.stan         # Stan model definition
│       ├── eight-schools.qmd  # Analysis document
│       ├── eight-schools.html # Rendered analysis
│       └── data-dictionary.csv # Model-specific data dictionary
├── README.md                  # This file
└── .gitignore                # Git ignore rules
```

### Directory Descriptions

**`.devcontainer/`**: Contains the complete Docker setup with recommended dependencies for running Bayesian models. Includes the `Dockerfile`, VS Code configuration (`devcontainer.json`), and dependency files for R and Python.

**`templates/`**: Base templates built following best practices for statistical modeling. Use these as starting points for new analyses.

**`models/`**: Individual folders for each model implementation. Each folder contains:
- `model.stan`: Stan code for the statistical model
- `{model-name}.qmd`: Quarto document with model execution and interpretation
- `{model-name}.html`: Rendered HTML output for easy viewing without re-running
- `data-dictionary.csv`: Data description specific to this model

Each model folder follows a consistent naming convention and structure to maintain organization as the number of models grows.

## Models

This section documents the different models implemented in the `models/` folder. Each model follows the Bayesian workflow and includes detailed analysis documentation.

### Model Registry

| Model ID | Description | Status |
|----------|-------------|---------|
| `eight-schools` | Eight schools model from Gelman et al. (2003) - hierarchical normal model for estimating treatment effects | Final model |

### Model Status Definitions

- **Prior contradicts domain knowledge**: Model rejected due to unrealistic prior assumptions
- **Computation is not valid**: Model rejected due to computational issues (convergence, sampling problems)
- **Model is not trustworthy**: Model rejected after failing model evaluation checks
- **Model is provisionally accepted**: Model passes all checks and is included in model comparison
- **Final model**: Selected model after comparison phase

### Adding New Models

To add a new model:

1. Create a new folder in `models/` with a descriptive name
2. Copy the template from `templates/bayesian-analysis.qmd`
3. Implement your Stan model in `model.stan`
4. Document your analysis in the `.qmd` file
5. Update this registry table with your model information

## Bayesian Workflow

This repository implements the Bayesian workflow proposed by Gelman et al. (2020), which provides a systematic approach to Bayesian data analysis.

![Bayesian Workflow](https://github.com/user-attachments/assets/da90a66a-c703-4e05-ac41-d8100cc35e6b)

### Workflow Steps

1. **Model Building**: Define your statistical model based on domain knowledge
2. **Prior Selection**: Choose appropriate prior distributions
3. **Computational Check**: Verify that your model runs correctly
4. **Model Evaluation**: Assess model fit and predictive performance
5. **Model Comparison**: Compare multiple candidate models
6. **Final Analysis**: Present results from the selected model

### Implementation

- Each model is documented in its own folder within `models/`
- The complete workflow process is documented in the associated `.qmd` file
- Once a model is provisionally approved, model comparison is carried out
- Templates ensure consistency across different analyses

## Prerequisites

- [Docker](https://www.docker.com/) (recommended) or local installation of R, Python, and Stan
- [VS Code](https://code.visualstudio.com/) with Dev Containers extension (recommended)
- Basic knowledge of Bayesian statistics and Stan

## Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork the repository** and create a feature branch
2. **Follow the established structure** for new models and analyses
3. **Use the provided templates** to maintain consistency
4. **Document your work thoroughly** in Quarto documents
5. **Test your models** in the development container
6. **Submit a pull request** with a clear description of your changes

## Troubleshooting

### Common Issues

**Container won't start**: Ensure Docker is running and you have sufficient disk space

**Stan compilation errors**: Check that your model syntax is correct and all required data is available

**Package conflicts**: The development container includes tested package versions; avoid installing additional packages without testing

**Memory issues**: Large models may require adjusting Docker memory limits

### Getting Help

- Check the [Stan documentation](https://mc-stan.org/users/documentation/) for modeling questions
- Review the [Quarto documentation](https://quarto.org/docs/) for document formatting
- Open an issue in this repository for project-specific questions

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## References

- Davidson-Pilon, C. (2015). *Bayesian Methods for Hackers: Probabilistic Programming and Bayesian Inference*. Addison-Wesley Professional.

- Gelman, A., Carlin, J. B., Stern, H. S., & Rubin, D. B. (2003). *Bayesian Data Analysis* (2nd ed.). CRC Press.

- Gelman, A., Vehtari, A., Simpson, D., Margossian, C. C., Carpenter, B., Yao, Y., Kennedy, L., Gabry, J., Bürkner, P. C., & Modrák, M. (2020). Bayesian workflow. *arXiv preprint arXiv:2011.01808*. https://doi.org/10.48550/arXiv.2011.01808

- Matsuura, K. (2022). *Bayesian Statistical Modeling with Stan, R, and Python* (Vol. 526). Springer.

- McElreath, R. (2018). *Statistical Rethinking: A Bayesian Course with Examples in R and Stan*. Chapman and Hall/CRC.

## Acknowledgments

This repository structure and workflow are inspired by the best practices outlined in the Bayesian statistics community and the recommendations from the Stan development team.
