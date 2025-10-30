# Data Directory

This directory is intended to store data files used in the Bayesian statistical modeling analyses.

## Structure

- **Raw data files**: Store original, unmodified data files here (e.g., CSV, Excel, etc.)
- **data-dictionary.csv**: A data dictionary describing all variables in your datasets

## Data Dictionary Format

The data dictionary should follow this format:

```csv
name; type; description
variable_name; Variable_Type; Description of the variable
```

Where:
- **name**: Variable name (lowercase, no spaces, use underscores)
- **type**: One of: Nominal, Ordinal, Continuous, or Discrete
- **description**: Clear description of what the variable represents

## Best Practices

1. **Never commit sensitive data**: Add sensitive data files to `.gitignore`
2. **Document data sources**: Include information about where data came from
3. **Version your data**: Consider using data versioning tools like DVC for large datasets
4. **Clean data**: Ensure data is properly formatted and cleaned before analysis
5. **ABT (Analytical Base Table)**: The data here should be analysis-ready

## Privacy and Security

- Do not commit personally identifiable information (PII)
- Do not commit credentials or API keys
- Consider using anonymized or synthetic data for examples
- Add sensitive data file patterns to `.gitignore`

## Example Data

For the eight-schools example, the data is embedded directly in the analysis file (`models/eight-schools/eight-schools.qmd`) rather than stored as a separate file, which is appropriate for small datasets.
