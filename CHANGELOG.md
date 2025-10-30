# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- LICENSE file (MIT License)
- CODE_OF_CONDUCT.md following Contributor Covenant
- CONTRIBUTING.md with detailed contribution guidelines
- .editorconfig for consistent code formatting across editors
- .gitattributes for proper line ending handling
- Enhanced .gitignore with comprehensive patterns for R, Python, Stan, and Quarto
- GitHub issue templates (bug report, feature request, model addition)
- GitHub pull request template
- GitHub Actions workflow for validating Quarto documents
- model-comparison.qmd template as referenced in README
- data/ directory structure with placeholder files
- README files for data/, models/, and templates/ directories
- Quick Start section in main README
- Key Features section with badges in main README
- Setup instructions in main README

### Changed
- Enhanced README with better structure and documentation
- Improved .gitignore to be more comprehensive

### Fixed
- Typo in README: "folloring" → "following"
- Typo in README: "attemped" → "attempted"
- Typo in README: "provissionaly" → "provisionally"
- Typo in README: "builded" → "built"
- Typo in template data-dictionary.csv: "Continous" → "Continuous"
- Typo in eight-schools data-dictionary.csv: "Continous" → "Continuous"
- Removed duplicate libv8-dev package in Dockerfile

## [1.0.0] - Initial Release

### Added
- Basic repository structure with .devcontainer setup
- Eight schools example model with Stan implementation
- Bayesian analysis Quarto template
- Docker development environment with R, Python, Stan, and Quarto
- Base documentation and README

---

[Unreleased]: https://github.com/PabloCoello/bayes-stat-modeling/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/PabloCoello/bayes-stat-modeling/releases/tag/v1.0.0
