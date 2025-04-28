# Commit & Pull Request Standardization
```
Commit convention tags are a standardized way to write commit messages in a Git
repository. They help organize and automate code versioning, making it easier to
understand and maintain the project's history.
```

## Commit Tags

- feat(TADocs-Dev): "description"
    - Used when a new feature or functionality is added to the project.
    Example - `feat(TADocs-Dev): add user authentication feature`

- fix(TADocs-Dev): "description"
    - Used for bug fixes or code issues.
    Example - `fix(TADocs-Dev): correct typo in user registration function`

- docs(TADocs-Dev): "description"
    - Used for changes related to project documentation, such as README, manuals, comments, etc.
    Example - `docs(TADocs-Dev): update README with installation instructions`

- style(TADocs-Dev): "description"
    - Used for changes that do not affect code logic, such as formatting, spacing, style fixes, or linter adjustments.
    Example - `style(TADocs-Dev): fix indentation in main.py`

- refactor(TADocs-Dev): "description"
    - Used when code is restructured or refactored without changing its behavior or functionality, aiming to improve readability or performance.
    Example - `refactor(TADocs-Dev): optimize database queries for better performance`

- test(TADocs-Dev): "description"
    - Used to add or modify tests, such as unit tests, integration tests, or automated tests.
    Example - `test(TADocs-Dev): add unit tests for user authentication module`

- ci(TADocs-Dev): "description"
    - Used for adjustments in configuration files related to continuous integration, such as GitHub Actions, Travis CI, CircleCI, etc.
    Example - `ci(TADocs-Dev): update GitHub Actions workflow for deployment`

- chore(TADocs-Dev): "description"
    - Used for tasks that do not fit into the previous categories, such as minor changes that do not directly affect the application.
    Example - `chore(TADocs-Dev): update dependencies in package.json`
