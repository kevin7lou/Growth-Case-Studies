# Growth-Case-Studies
Growth Case Studies in Data Science

## Project Structure

```
.
├── .gitignore
├── README.md
├── data/              # Contains raw or processed data files
│   └── .gitkeep
├── notebooks/         # Contains Jupyter notebooks for case studies
│   ├── risk_control/
│   │   └── .gitkeep
│   └── user_growth/
│       └── .gitkeep
├── pyproject.toml     # Poetry configuration and dependencies
├── requirements.txt   # Dependencies for Google Colab
└── src/               # Source code for reusable functions/classes
    └── __init__.py
```

## Local Setup (Poetry)

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/<YOUR_USERNAME>/Growth-Case-Studies.git
    cd Growth-Case-Studies
    ```
2.  **Install Poetry** (if you haven't already):
    Follow the instructions on the [official Poetry website](https://python-poetry.org/docs/#installation).
3.  **Install dependencies:**
    This command creates a virtual environment and installs the packages listed in `pyproject.toml`.
    ```bash
    poetry install
    ```
4.  **Activate the virtual environment:**
    ```bash
    poetry shell
    ```
5.  **Launch Jupyter Lab:**
    ```bash
    jupyter lab
    ```
    You can now navigate to the `notebooks/` directory and run the case studies.

## Usage with Google Colab

You can run the notebooks directly in Google Colab without any local setup by clicking the "Open in Colab" badge.

**Example:**

To add a Colab badge for a notebook located at `notebooks/user_growth/example_growth_study.ipynb`, you would add the following Markdown to your `README.md` or directly into another notebook:

```markdown
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<YOUR_USERNAME>/Growth-Case-Studies/blob/main/notebooks/user_growth/example_growth_study.ipynb)
```

**Remember to replace `<YOUR_USERNAME>` with your actual GitHub username.**

**Important:** Each notebook intended for use in Colab should include the following code cell at the beginning to install the necessary dependencies:

```python
# Install dependencies if running in Colab
import sys
if 'google.colab' in sys.modules:
    # Clone the repo to access requirements.txt and potential data/src files
    !git clone https://github.com/<YOUR_USERNAME>/Growth-Case-Studies.git temp_repo
    !pip install -q -r temp_repo/requirements.txt
    # Add src directory to Python path (optional, if you use src)
    sys.path.insert(0, 'temp_repo/src')
    # Change working directory (optional, if notebooks access data relative to repo root)
    %cd temp_repo
    # Note: You might need to adjust data loading paths in the notebook
    #       e.g., instead of '../data/file.csv', use 'data/file.csv'
    #       after changing directory.
```

This cell first checks if the code is running in Colab. If so, it clones the repository temporarily (to access `requirements.txt` and potentially data or source files), installs the dependencies using `pip`, and optionally adjusts the Python path and working directory.
