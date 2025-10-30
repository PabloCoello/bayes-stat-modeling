# Models Directory

This directory contains individual Bayesian statistical models following the workflow proposed by Gelman et al. (2020).

## Directory Structure

Each model should be in its own subdirectory with the following structure:

```
models/
├── model-name/
│   ├── model.stan           # Stan model code
│   ├── model-name.qmd       # Quarto analysis document
│   ├── model-name.html      # Rendered output (generated)
│   └── data-dictionary.csv  # Variable descriptions
```

## Creating a New Model

1. **Create a new directory** with a descriptive name (use lowercase and hyphens)
   ```bash
   mkdir models/my-new-model
   cd models/my-new-model
   ```

2. **Copy the template** from `templates/bayesian-analysis.qmd`
   ```bash
   cp ../../templates/bayesian-analysis.qmd my-new-model.qmd
   ```

3. **Create the Stan model file** (`model.stan`)
   - Define your data block
   - Define parameters
   - Specify priors and likelihood

4. **Create the data dictionary** (`data-dictionary.csv`)
   - Follow the format in `templates/data-dictionary.csv`

5. **Complete the analysis** in the `.qmd` file following these sections:
   - Context and Goals
   - Data (including EDA)
   - Model (formula and implementation)
   - Results interpretation
   - References

6. **Update the main README** to include your model in the models table

## Analysis Workflow

Follow the Bayesian workflow diagram from Gelman et al. (2020):

1. **Problem formulation**: Define the research question
2. **Model building**: Specify priors and likelihood
3. **Computational faithfulness**: Ensure the model compiles and runs
4. **Model adequacy**: Check if model fits the data
5. **Model comparison**: Compare with alternative models (if applicable)
6. **Model understanding**: Interpret results and communicate findings

## Model Status

Each model should be tagged with one of the following statuses in the main README:

- **Prior contradicts domain knowledge**: Priors are not appropriate
- **Computation is not valid**: Model fails computational checks
- **Model is not trustworthy**: Model fails evaluation checks  
- **Model is provisionally accepted**: Ready for comparison
- **Final model**: Selected as the best model

## Example: Eight Schools

The `eight-schools` directory contains a complete example implementing the classic eight schools hierarchical model. Use it as a reference for creating your own models.

## Best Practices

1. **Use meaningful names**: Choose descriptive model directory names
2. **Document thoroughly**: Include context, assumptions, and interpretations
3. **Check diagnostics**: Always verify convergence (R-hat, ESS, trace plots)
4. **Visualize results**: Include posterior predictive checks and parameter plots
5. **Cite references**: Acknowledge sources and related work
6. **Version control**: Commit working versions regularly

## Resources

- [Stan User's Guide](https://mc-stan.org/docs/stan-users-guide/)
- [Bayesian Workflow paper](https://arxiv.org/abs/2011.01808)
- [Stan Best Practices](https://mc-stan.org/docs/stan-users-guide/best-practices.html)
