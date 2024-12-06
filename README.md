# bayes-stat-modeling
This repository is dedicated to hosting examples of statistical modeling using the Bayesian approach. Additionally, it also includes templates for documenting analyses with best practices, useful references, and an execution environment for analyses with validated dependencies.

# Structure of this repo
This repo is organized in the following fashion:

```plaintext
bayes-stat-modeling/
├── .devcontainer/
│   ├── Dockerfile
│   ├── devcontainer.json
│   ├── requirements/
│   │   ├── requirements.txt
│   │   ├── requirements-src.R
│   │   └── requirements-bin.txt
├── models/
│   ├── modelname/.py
│   │   ├── model.stan
│   │   └── modelname.qmd
│   └── .../
├── templates/
│   └── bayesian-analysis.md
├── README.md
└── .gitignore
```

The `.devcontainer` folder contains the entire setup for the Docker container with the recommended dependencies to run the models. Inside, we can find the corresponding `Dockerfile`, the `devcontainer.json` with the configurations for the VSCode IDE, and the `requirements` folder, which contains the files with dependencies for R and Python.

The `models` folder contains individual folders for each project/model. Each of these folders is named with the identifier of the respective project. Inside each folder, you'll find the `model.stan` file with the Stan code for the modeling, and the `"modelname".qmd` file, a Quarto file where the model is executed and interpreted for both R and Python. Additionally, the `"modelname".html` file contains the result of rendering the qmd file, allowing us to consult the analysis without needing to re-run it.

The `templates` folder contains base templates builded following good practices to follow at the time of building statistical models.

# Models

| Model id | Author/reference |Description |
|---|---|---|
| eight-schools | Gelman et al (2003) |  |
|   |   |   |
|   |   |   |

# References
* Davidson-Pilon, C. (2015). Bayesian methods for hackers: probabilistic programming and Bayesian inference. Addison-Wesley Professional.
* Gelman, A., Carlin, J. B., Stern, H. S., and Rubin, D. B. (2003). Bayesian Data Analysis, CRC Press, London, 2nd Edition.
* Matsuura, K. (2022). Bayesian Statistical Modeling with Stan, R, and Python (Vol. 526). Springer.
* McElreath, R. (2018). Statistical rethinking: A Bayesian course with examples in R and Stan. Chapman and Hall/CRC.
