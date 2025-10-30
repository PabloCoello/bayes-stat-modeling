# Security Policy

## Supported Versions

This project is currently in active development. We recommend using the latest commit from the main branch.

| Version | Supported          |
| ------- | ------------------ |
| Latest  | :white_check_mark: |
| Older   | :x:                |

## Reporting a Vulnerability

If you discover a security vulnerability in this repository, please follow these steps:

1. **Do NOT** open a public issue
2. Send a description of the vulnerability to the repository maintainers via:
   - GitHub Security Advisory (preferred): Use the "Security" tab → "Report a vulnerability"
   - Or create a private issue with the maintainers

3. Include the following information:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if available)

## Security Best Practices for Users

When using this repository:

1. **Never commit sensitive data**:
   - API keys
   - Passwords
   - Personal identifiable information (PII)
   - Private datasets

2. **Use the dev container**: The provided Docker container includes validated dependencies

3. **Review dependencies**: Check the `.devcontainer/requirements/requirements.txt` and `.devcontainer/requirements/requirements-src.R` files for security updates

4. **Keep Docker updated**: Ensure you're using recent versions of Docker and the base images

5. **Data privacy**: 
   - Anonymize data before adding to the repository
   - Use `.gitignore` to exclude sensitive files
   - Consider using data versioning tools like DVC for large datasets

## Dependency Security

We monitor dependencies for security vulnerabilities:

- **Python packages**: Listed in `.devcontainer/requirements/requirements.txt`
- **R packages**: Listed in `.devcontainer/requirements/requirements-src.R` and `requirements-bin.txt`
- **System packages**: Managed via Dockerfile

To update dependencies:
```bash
# For Python
pip list --outdated

# For R
install.packages("package_name")
```

## Docker Security

The Dockerfile in this repository:
- Uses Ubuntu 20.04 LTS as base (consider upgrading to 22.04 or 24.04 for newer security patches)
- Installs system packages from official repositories

**Security Note**: The Dockerfile contains SSH key build arguments that are written to image layers. While these keys are removed from the final filesystem, they may still be accessible in the image history. For production use:
- Build images without SSH keys or use multi-stage builds
- Use secret management features like Docker BuildKit secrets
- Avoid committing sensitive credentials to the Dockerfile

## Acknowledgments

We appreciate responsible disclosure of security vulnerabilities and will acknowledge contributors in our release notes (unless they prefer to remain anonymous).
