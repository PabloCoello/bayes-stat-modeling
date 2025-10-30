# Templates Directory

This directory contains templates to help you create well-structured Bayesian analyses following best practices.

## Available Templates

### bayesian-analysis.qmd

A comprehensive Quarto template for Bayesian statistical modeling that follows the workflow proposed by Gelman et al. (2020).

**Sections included:**
1. **Context and Goals**: Describe the problem and objectives
2. **Data**: Document variables and perform exploratory analysis
3. **Model**: Specify the mathematical model and implement it
4. **Interpret Results**: Present findings and conclusions
5. **References**: Cite relevant sources

**How to use:**
```bash
# Copy template to your model directory
cp templates/bayesian-analysis.qmd models/your-model/your-model.qmd
```

### data-dictionary.csv

A template for documenting your data variables.

**Format:**
```csv
name; type; description
variable_name; Variable_Type; Description of the variable
```

**Variable types:**
- **Nominal**: Categorical values without order
- **Ordinal**: Categorical values with ranking
- **Continuous**: Numeric values on a continuous scale
- **Discrete**: Numeric values in countable units

**Example:**
```csv
name; type; description
age; Continuous; Age of participant in years
treatment_group; Nominal; Experimental group assignment (control/treatment)
response_score; Ordinal; Survey response on 5-point Likert scale
num_visits; Discrete; Number of clinic visits
```

## Customizing Templates

Feel free to customize these templates for your specific needs while maintaining the core structure:

1. **Keep the workflow sections**: The main analysis sections follow the Bayesian workflow
2. **Add project-specific content**: Adapt to your domain and requirements
3. **Maintain documentation**: Keep the data dictionary up to date
4. **Follow code style**: Use consistent formatting (see `.editorconfig`)

## Rendering Templates

To preview the template:

```bash
cd templates
quarto render bayesian-analysis.qmd
```

This will generate an HTML file showing the template structure.

## Best Practices

1. **Start with the template**: Don't build analyses from scratch
2. **Fill in all sections**: Complete documentation helps reproducibility
3. **Update as you go**: Keep documentation synchronized with your analysis
4. **Version control**: Track changes to understand your analysis evolution
5. **Share templates**: If you create useful variations, consider contributing them

## Contributing New Templates

If you develop a specialized template (e.g., for time series, survival analysis, etc.), consider contributing it:

1. Create the template file in this directory
2. Document it in this README
3. Submit a pull request following [CONTRIBUTING.md](../CONTRIBUTING.md)

## Resources

- [Quarto Documentation](https://quarto.org/)
- [Bayesian Data Analysis Book](http://www.stat.columbia.edu/~gelman/book/)
- [Stan Documentation](https://mc-stan.org/users/documentation/)
