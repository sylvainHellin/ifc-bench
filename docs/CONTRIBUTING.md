# Contributing to ifc-bench

We welcome contributions to the `ifc-bench` dataset! This document outlines the guidelines for contributing new models, QA pairs, documentation, or code improvements.

## How to Contribute

### 1. Reporting Issues

If you find a bug, an error in the dataset, or have a suggestion, please open an issue on our [GitHub issue tracker](https://github.com/sylvainHellin/ifc-bench/issues).

### 2. Contributing New IFC Models

We are always looking for new IFC models to expand the dataset. When contributing a new model, please ensure: 

-   **Licensing**: The model must be available under a permissive open-source license (e.g., CC BY 4.0, MIT).
-   **Format**: The model must be in the IFC format.
-   **Documentation**: Provide a brief description of the model, including its purpose, size, and complexity.
-   **Organization**: Place the model files in a new folder under the `models/` directory. Include a `license.txt` file with the model's license.
-   **QA Pairs** (Optional): Include question-answer pairs for the new model.

### 3. Contributing New QA Pairs

If you want to add more question-answer pairs to existing models:

-   **Format**: Add new rows to the `questions/ifc-bench-v1.csv` file.
-   **Accuracy**: Ensure the answers are accurate and verifiable.
-   **Clarity**: Questions should be clear and unambiguous.
-   **Diversity**: Try to cover different aspects of the model (spatial, properties, systems, etc.).
-   **Consistency**: Follow the existing format for questions, answers, model identifiers, and project categories.

### 4. Correcting Existing Answers
If you find inaccuracies in existing QA pairs:
- **Verification**: Provide evidence for the correction (screenshots, model measurements)
- **Format**: Modify the answer cell in `questions/ifc-bench-v1.csv` while keeping the original question
- **Traceability**: Include a brief explanation in the pull request description

### 5. Contributing Documentation

If you want to improve the documentation:

-   **Clarity**: Ensure the documentation is clear, concise, and easy to understand.
-   **Accuracy**: Ensure the documentation is accurate and up-to-date.
-   **Format**: Follow the Markdown format.
-   **Organization**: Place new documentation files in the `docs/` directory.


## Contribution Workflow

1.  **Fork the repository** on GitHub.
2.  **Create a new branch** for your changes.
3.  **Make your changes** and commit them with clear messages.
4.  **Push your branch** to your forked repository.
5.  **Submit a pull request** to the main repository.


## Questions

If you have any questions, please open an issue on our [GitHub issue tracker](https://github.com/sylvainHellin/ifc-bench/issues).

**Before starting major work:**
- Check open issues for existing discussions
- For large contributions, consider opening an issue first to discuss the approach

Thank you for your contributions!
