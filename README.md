# Interactive Fiction Environment Analysis

This repository contains code for analyzing and interacting with datasets related to interactive fiction. It uses a dataset from the "LIGHT" environment, which contains information about characters, rooms, objects, and their relationships. Additionally, it demonstrates how to use language models like OpenAI to generate and evaluate fantasy items for text-based adventure games.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Setup and Requirements](#setup-and-requirements)
- [Usage](#usage)
- [Data Loading and Exploration](#data-loading-and-exploration)
- [Fine-Tuning Data Preparation](#fine-tuning-data-preparation)
- [Fine-Tuning GPT Models](#fine-tuning-gpt-models)
- [Zero-shot, One-shot, and Few-shot Prompting](#zero-shot-one-shot-and-few-shot-prompting)
- [Evaluation](#evaluation)
- [Key Observations](#key-observations)
- [Conclusion](#conclusion)
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

## Data Loading and Exploration

The script loads the LIGHT dataset in JSON format, which includes:
- **Categories:** Classifications like "Graveyard," "Forest," etc.
- **Rooms:** Represent game settings, including descriptions, characters, objects, and neighboring rooms.
- **Characters:** Defined by type (e.g., person, creature), descriptions, and inventory.
- **Objects:** Includes properties like `is_container`, `is_weapon`, etc.

### Key Functions
- `get_categories()`: Retrieves all categories from the dataset.
- `print_rooms_for_category(category)`: Lists rooms under a specific category.
- `make_connections()`: Displays connections between rooms (as a graph structure).
- `count_character_types()`: Summarizes the number of each type of character in the dataset.

---

## Fine-Tuning Data Preparation

The script prepares data for fine-tuning OpenAI GPT models using the LIGHT dataset.

### Steps:
1. **Location Descriptions:**
   - Extracts `category`, `setting`, and `description` for rooms.
   - Creates JSONL data with:
     - `prompt`: Category + setting.
     - `completion`: Room description.

2. **Object Properties:**
   - Extracts object names, descriptions, and properties (`is_weapon`, `is_food`, etc.).
   - Creates JSONL data with:
     - `prompt`: Item information.
     - `completion`: True/False for each property.

### Output
- JSONL files are generated for fine-tuning, such as `fine_tuning_location_descriptions.jsonl`.

---

## Fine-Tuning GPT Models

The script uses OpenAI's API to fine-tune models like `babbage-002`.

### Workflow:
1. Uploads training data via the OpenAI API.
2. Creates fine-tuning jobs with training files.
3. Evaluates the fine-tuned model’s performance.

### Key Models
- Fine-tuning is demonstrated with models like `babbage-002`.

---

## Zero-shot, One-shot, and Few-shot Prompting

The script experiments with different prompting strategies to determine object properties:
- **Zero-shot:** Queries the model directly without examples.
- **One-shot:** Provides one example before querying the model.
- **Five-shot:** Provides multiple examples to guide the model.

### Prompts Include:
- Item name and description.
- A list of properties (e.g., `is_weapon`, `is_food`).
- The model predicts True/False for each property.

---

## Evaluation

The script evaluates fine-tuned and one-shot models using **precision** and **recall** metrics.

### Steps:
1. Generate predictions for object properties.
2. Compare predictions with true labels from the dataset.
3. Calculate precision and recall for each property (e.g., `is_gettable`, `is_weapon`).

### Metrics:
- **Precision:** Proportion of correctly predicted properties out of all predictions.
- **Recall:** Proportion of correctly predicted properties out of all true properties.

---

## Key Observations
1. **Data-Driven Approach:** The script thoroughly explores the dataset, analyzing categories, rooms, characters, and objects.
2. **Fine-Tuning Workflow:** Demonstrates a complete process for preparing and fine-tuning OpenAI GPT models.
3. **Evaluation Framework:** Implements precision and recall metrics to evaluate model performance.

---

## Conclusion

The script provides a comprehensive framework for leveraging the LIGHT dataset in interactive fiction research. It demonstrates how fine-tuned and prompted GPT models can enhance game development by generating and analyzing game elements.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
