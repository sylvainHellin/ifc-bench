# ifc-bench 🏗️💡
![Dataset Version](https://img.shields.io/badge/version-v1.0-blue)

A benchmark dataset for evaluating BIM (Building Information Modeling) comprehension and reasoning capabilities in AI systems. Provides curated IFC models with question-answer pairs for testing BIM-related AI implementations.

**Dataset snapshot:**
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>question</th>
      <th>answer</th>
      <th>ifc_model</th>
      <th>project</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>What is the total gross floor area of the buil...</td>
      <td>The total gross floor area of the building is ...</td>
      <td>arc</td>
      <td>duplex</td>
    </tr>
    <tr>
      <th>1</th>
      <td>What is the height of the ceiling in room A203?</td>
      <td>The height of the ceiling in room A203 is 2.58 m</td>
      <td>arc</td>
      <td>duplex</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Give me the name of all the rooms in the build...</td>
      <td>The list of all the rooms in the building is: ...</td>
      <td>arc</td>
      <td>duplex</td>
    </tr>
    <tr>
      <th>3</th>
      <td>How many windows are there on the north facade?</td>
      <td>I cannot calculate the number of window on th...</td>
      <td>arc</td>
      <td>duplex</td>
    </tr>
    <tr>
      <th>4</th>
      <td>What is the width of the door 1hOSvn6df7F8_7Gc...</td>
      <td>The width of the door is 1.25 m</td>
      <td>arc</td>
      <td>duplex</td>
    </tr>
  </tbody>
</table>
</div>


## Table of Contents
- [Features](#features)
- [Dataset Structure](#dataset-structure)
- [Getting Started](#getting-started)
- [Models Overview](#models-overview)
- [Contributing](#contributing)
- [License](#license)
- [Citation](#citation)
- [Acknowledgments](#acknowledgments)

## Features

- **Versioned datasets**: Currently at V1 with 2 BIM models and 105 QA pairs
- **Diverse question types**:
  - Spatial reasoning
  - Element properties
  - System relationships
  - Construction sequencing
- **Rich contextual data**:
  - Original IFC files
  - Model snapshots
  - Architectural descriptions
  - License documentation
- **Machine-readable format**: CSV dataset with clear column structure

## Dataset Structure

```
ifc-bench/
├── projects/                  # Directory for all projects
│   ├── duplex/                # First project
│   │   ├── arc.ifc            # Architecture model
│   │   ├── mep.ifc            # MEP model
│   │   ├── license.txt        # Project license
│   │   ├── model_card.csv     # Project metadata
│   │   └── snapshot.png       # Visual snapshot
│   └── dental_clinic/         # Second project
│       ├── arc.ifc            # Architecture model
│       ├── str.ifc            # Structural model
│       ├── mep.ifc            # MEP model
│       └── ...                # Other project files
├── questions/                  # Question-answer pairs
│   └── ifc-bench-v1.csv       # Primary dataset
└── docs/                      # Supplementary materials
    └── CONTRIBUTING.md        # Contribution guidelines
```

## Models Overview

### 🏠 Duplex Model
- **Disciplines**: Architectural, MEP
- **License**: [CC-BY-4.0](models/duplex/license.txt)
- **Complexity**: Simple
- **Source**: [buildingSMART Sample Files](https://github.com/buildingsmart-community/Community-Sample-Test-Files)

![Duplex model snapshot](models/duplex/snapshot.png)

### 🏥 Dental Clinic
- **Disciplines**: Architectural, Structural, MEP
- **License**: [CC-BY-4.0](models/dental_clinic/license.txt)
- **Complexity**: Intermediate
- **Source**: [buildingSMART Sample Files](https://github.com/buildingsmart-community/Community-Sample-Test-Files)

![Dental Clinic model snapshot](models/dental_clinic/snapshot.png)

## Getting Started

### Prerequisites
- Python 3.8+
- pandas (for data analysis)
- ifcopenshell (optional, for working with IFC files)

Install requirements:
```bash
pip install pandas ifcopenshell
```

### Quick Start
```bash
git clone https://github.com/sylvainHellin/ifc-bench.git
cd ifc-bench
```

### Using the Dataset
```python
import pandas as pd

# Load dataset
df = pd.read_csv('questions/ifc-bench-v1.csv')

# Explore questions by model
duplex_questions = df[df['ifc_model'] == 'duplex']
print(f"Duplex model has {len(duplex_questions)} questions")

# Sample question format
sample_q = df.iloc[0]
print(f"""
Question: {sample_q.question}
Answer: {sample_q.answer}
Model: {sample_q.ifc_model}
Project: {sample_q.project}
""")
```

### Dataset Columns
| Column | Description | Example |
|--------|-------------|---------|
| `question` | Natural language question | "What is the total gross floor area of the building?" |
| `answer` | Ground truth answer | "The total gross floor area of the building is 354.67 sqm" |
| `ifc_model` | Model identifier | "arc" |
| `project` | Question category | "duplex" |

## Dataset Integrity
Verify dataset integrity using SHA-256 checksum:

```bash
shasum -a 256 questions/ifc-bench-v1.csv
# Expected output: f67a48770d74b6e0ff0868c923c3e1d976110350b2c439564d7ceccc16a46f35
```

## Contributing

We welcome contributions through:
- 🆕 New IFC models (with permissive licensing)
- ➕ Additional QA pairs for existing models
- ✏️ Documentation improvements
- 🐛 Error corrections in existing answers

Please see our [Contribution Guidelines](docs/CONTRIBUTING.md) for details.

## License

- **Dataset**: Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- **Models**: Inherit their original licenses (see individual model folders)

## Citation

If using in research, please cite:
```bibtex
@misc{ifc-bench,
  title = {{ifc-bench}: {BIM} Comprehension \& Reasoning Benchmark Dataset},
  author = {Sylvain Hellin},
  year = {2024},
  url = {https://github.com/sylvainHellin/ifc-bench},
  note = {Version 1.0}
}
```

## Acknowledgments

Special thanks to:
- [buildingSMART International](https://www.buildingsmart.org/) for providing sample files
- The openBIM community for quality assurance
- Early adopters for feedback and validation

---

**📌 Maintainer**: Sylvain Hellin | **📧 Contact**: [sylvain.hellin@tum.de](mailto:sylvain.hellin@tum.de) | **🐛 Issue Tracker**: [GitHub Issues](https://github.com/sylvainHellin/ifc-bench/issues)
