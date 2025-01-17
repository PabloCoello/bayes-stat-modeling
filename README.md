# bayes-stat-modeling
This repository is dedicated to host analysis following the bayesian workflow proposed by (Gelman et al., 2020). Additionally, it also includes templates for documenting analyses with best practices, useful references, and an execution environment with validated dependencies.

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
├── templates/
│   ├── bayesian-analysis.qmd
├── models/
│   ├── model1/
│   │   ├── model.stan
│   │   └── model1-analysis.qmd
│   ├── model2/
│   │   ├── model.stan
│   │   └── model2-analysis.qmd
│   └── .../
├── data/
│   └── data-file.csv
│   └── data-dictionary.csv
├── model-comparison.qmd
├── README.md
└── .gitignore
```

The `.devcontainer` folder contains the entire setup for the Docker container with the recommended dependencies to run the models. Inside, we can find the corresponding `Dockerfile`, the `devcontainer.json` with the configurations for the VSCode IDE, and the `requirements` folder, which contains the files with dependencies for R and Python.

The `models` folder contains individual folders for each modelization. Each of these folders is named with the identifier of the respective model. Inside each folder, you'll find the `model.stan` file with the Stan code for the modeling, and the `"modelname".qmd` file, a Quarto file where the model is executed and interpreted for both R and Python. Additionally, the `"modelname".html` file contains the result of rendering the qmd file, allowing us to consult the analysis without needing to re-run it. There are as many models folders as different modelizations we are willing to test in our data.

The `templates` folder contains base templates builded following good practices to follow at the time of building statistical models.

The `data` folder contains the data required for the analysis in case that we are willing to store it locally. It also contains the data dictionary with information to understand the data files.

`report.qmd` summarizes the final results of our analysis after applying and comparing all the models in the `models` folder.

# Models
It is recommended to detail in this space the different models that have been applied in the 'models' folder to allow for quick access in the future.

| Model id |Description | Result |
|---|---|---|
| eight-schools | Eight schools model estimated in Gelman et al (2003) | Final model |

The fields in the table should be filled with the folloring information:

* **Model id**: A short code or name for an specific modelization.
* **Description**: A short description o what was attemped in this specific modelization that is different from the others.
* **Result**: One of the following possible results:
  * __Prior contradicts domain knowledge__: This model is not provisionally accepted because priors contradict domain knowledge.
  * __Computation is not valid__: This model is not provisionally accepted because it didn't pass the computation check.
  * __Model is not trustworthy__: This model is not provisionally accepted because it didn't pass the evaluation check.
  * __Model is provissionaly accepted__: This model is provisionally accepted and is considered in the model comparison step.
  * __Final model__: This is the final modelization for our analysis.

# How to use this repository
This repository has been designed to work with the Bayesian workflow proposed by (Gelman et al., 2020).

![image](https://github.com/user-attachments/assets/da90a66a-c703-4e05-ac41-d8100cc35e6b)

For each model, the entire process will be documented in the associated folder within the `Models` folder. Once the model is provisionally approved, the model comparison step will be carried out in the `model-comparison.qmd` file.

# References
* Davidson-Pilon, C. (2015). Bayesian methods for hackers: probabilistic programming and Bayesian inference. Addison-Wesley Professional.
* Gelman, A., Carlin, J. B., Stern, H. S., and Rubin, D. B. (2003). Bayesian Data Analysis, CRC Press, London, 2nd Edition.
* Gelman, A., Vehtari, A., Simpson, D., Margossian, C. C., Carpenter, B., Yao, Y., ... & Modrák, M. (2020). Bayesian workflow. arXiv preprint arXiv:2011.01808.
* Matsuura, K. (2022). Bayesian Statistical Modeling with Stan, R, and Python (Vol. 526). Springer.
* McElreath, R. (2018). Statistical rethinking: A Bayesian course with examples in R and Stan. Chapman and Hall/CRC.
