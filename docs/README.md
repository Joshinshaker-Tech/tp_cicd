# jmt_cicd
The language-independent template for JMT CI/CD projects. Language-specific templates will be created based off of this template.

# Using This Template:
This template should not be used on its own, where possible. Instead, a language or stack-specific 
template should be created based on it, including:
- GitHub Actions automations including:
    - Testing
    - Security Analysis
    - Linting
    - Code Formatting
    - Performance Analysis
- Base source code files.
- Dependency management.
- Git hooks including everything that the github actions do.
- Gitignore
- Anything else that the language may need.