# Research Paper Intelligent System
This project uses a Transformer-based model to automatically generate potential research gaps from the title and abstract of a scientific paper. By analyzing the input text, the system synthesizes novel areas for future investigation, acting as a powerful tool for students, academics, and researchers.

## Evaluation and Performance
The model's performance was evaluated on its ability to generate relevant and coherent text. The full report is available [here](https://github.com/Abasar03/Research-Paper-Intelligent-System/blob/main/results/final_evaluation_report.json).

The key aggregate metrics are summarized below:

| Metric                | Mean Score |
|-----------------------|------------|
| ROUGE-1               | 0.052      |
| ROUGE-2               | 0.000      |
| ROUGE-L               | 0.048      |
| Semantic Similarity   | 0.265      |
| Overall Quality Score | 0.392      |


## Performance Graph
The training and validation loss over epochs are visualized [here](https://github.com/Abasar03/Research-Paper-Intelligent-System/blob/main/results/loss_curve.png), indicating that the model learned the underlying patterns in the data without significant overfitting.

## Limitations and Future Work
### Current Limitations
- **Domain-Specific Training:** The model is currently trained exclusively on a dataset of Computer Science research papers. As a result, its performance on papers from other academic domains will be significantly limited, and the generated text may not be relevant.

- **Interpreting the Evaluation Scores:** The relatively low ROUGE and similarity scores are indicative of the immense difficulty of the task. Generating novel, high-quality academic text is a significant challenge for language models. These scores should be seen as a baseline for an early-stage experimental model, highlighting areas for future improvement rather than a failure of the approach.

### Future Work
- **Improving Model Performance:** The next steps involve fine-tuning the model on a larger, more diverse dataset and experimenting with different architectures to improve the coherence and relevance of the generated text.

- **Expanding to Other Domains:** I plan to train and validate the model on datasets from various academic fields to create a more versatile and robust tool.

- **Similar Paper Recommendation:** A key future feature will be to implement a recommendation engine. After a user provides a paper, the system will not only generate a research gap but also suggest a list of semantically similar research papers, providing a more comprehensive research discovery tool.

## Getting Started
This project is designed to be run in a Google Colab environment, as it leverages a pre-trained model saved in Google Drive for evaluation. You can also run it locally if you have the necessary hardware.
### Option 1: Run on Google Colab (Recommended)
This is the most straightforward method, as Colab provides the necessary GPU environment and seamless integration with Google Drive. Follow these steps:

1. **Download the Pre-trained Model:** First, download the research_gap_epoch_10_model.pt from the Releases page of this repository.

2. **Upload to Your Google Drive:** Upload the downloaded research_gap_epoch_10_model.pt file to your personal Google Drive.

3. **Open in Google Colab:** Upload the evaluation.ipynb notebook to Colab.

4. **Mount Google Drive:**  Run the following code cell to give your notebook access to the files in your Google Drive, including the model you uploaded.
```python
from google.colab import drive
drive.mount('/content/drive')
```

5. **Update the Model Path:** Update the file path to match the location where the model is saved in Google Drive.
```python
model_path = '/content/drive/MyDrive/research_gap_epoch_10_model.pt'
```
6. **Install Dependencies:** Run the following command in a cell to install all necessary packages:
```python
!pip install -r requirements.txt
```

7. **Run the Notebook:** You can now execute the remaining cells to load the model and perform the evaluation.


### Option 2: Run locally with a GPU
If you prefer to run the project locallu, ensure the the following prerequisites are met before proceeding.
- **GPU**: NVIDIA GPU (e.g., GTX 1650 or higher) with CUDA installed.  
- **Python**: Version 3.10 or newer.  

1. **Clone the Repository:**
```bash
git clone https://github.com/Abasar03/Research-Paper-Intelligent-System.git
cd "Research Paper Intelligent System"
```

2. **Download the Pre-trained Model:** Now, download the research_gap_epoch_10_model.pt from the Releases page of this repository and place it inside the project folder you just cloned.


3. **Create and activate a virtual environment:**
```bash
# Create the environment
python -m venv venv

# Activate it on Windows
venv\Scripts\activate

# Or on Linux/macOS
source venv/bin/activate
```

4. **Install required packages:**
```bash
pip install -r requirements.txt
```

5. **Run the Notebook:** Launch a local Jupyter server and open the evaluation.ipynb notebook. Ensure the file path to the pre-trained model is correct for your local setup.

## Directory Structure
```
└── research-paper-intelligent-system/
    ├── results/
    │   ├── final_evaluation_report.json
    │   ├── final_report.png
    │   └── loss_curve.png
    ├── .gitignore
    ├── data_preprocessing.ipynb
    ├── evaluation.ipynb
    ├── README.md
    ├── requirements.txt
    └── training.ipynb
```