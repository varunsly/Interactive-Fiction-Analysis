# Interactive Fiction Environment Analysis

This repository contains code for analyzing and interacting with datasets related to interactive fiction. It uses a dataset from the "LIGHT" environment, which contains information about characters, rooms, objects, and their relationships. Additionally, it demonstrates how to use language models like OpenAI to generate and evaluate fantasy items for text-based adventure games.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Setup and Requirements](#setup-and-requirements)
- [Usage](#usage)
- [Dataset Information](#dataset-information)
- [Code Overview](#code-overview)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project aims to provide an analysis toolset for the LIGHT interactive fiction environment, a fantasy world used for AI training and storytelling. The code allows you to explore the relationships between rooms, characters, and objects, while leveraging machine learning models to improve interaction and storytelling capabilities.

## Features
- Download and parse LIGHT dataset (characters, rooms, objects).
- Analyze categories and relationships between different elements of the environment.
- Implement functions to count character types, categorize rooms, and extract properties of objects.
- Utilize language models (OpenAI) to generate descriptions and evaluate the generated text against a gold standard.
- Compare fine-tuned and one-shot model results using precision and recall metrics.

## Setup and Requirements
To run the code in this repository, you will need:

- Python 3.8 or above
- Jupyter Notebook
- Required Python packages:
  - `requests`
  - `numpy`
  - `pandas`
  - `scikit-learn`
  - `openai`
  - `asyncio`

You can install the required packages using the following command:

```sh
pip install requests numpy pandas scikit-learn openai
```

## Usage

1. Clone the repository to your local machine:
   
   ```sh
   git clone https://github.com/your_username/interactive-fiction-analysis.git
   cd interactive-fiction-analysis
   ```

2. Run the Jupyter Notebook (`hw2.ipynb`) to execute the data analysis, item generation, and evaluation processes.

3. Update your OpenAI API key in the relevant code cells to use the GPT models for text generation.

## Dataset Information

The dataset used in this project is the LIGHT environment dataset, which consists of:
- **Rooms**: Different locations within the LIGHT world.
- **Characters**: Inhabitants of the LIGHT world with different properties.
- **Objects**: Items that can be found, used, or interacted with in different rooms.

The dataset is sourced from an online repository, and the project downloads it using `wget` and `curl` commands.

## Code Overview

- **Data Loading**: The dataset is loaded from JSON files and parsed to extract relevant information about rooms, characters, and objects.
- **Data Analysis**: Various analysis functions are provided, such as:
  - Getting categories of rooms.
  - Grouping rooms by their categories.
  - Extracting and counting character types.
- **Machine Learning Integration**: The project uses the OpenAI API to generate and evaluate item descriptions for interactive fiction:
  - Fine-tuned and one-shot models are compared using precision and recall.
- **Evaluation Metrics**: The results of the text generation models are evaluated based on how well they predict the properties of objects.

## Contributing

Feel free to open issues or submit pull requests. Contributions are always welcome!

## License

This project is licensed under the MIT License. See the LICENSE file for details.
