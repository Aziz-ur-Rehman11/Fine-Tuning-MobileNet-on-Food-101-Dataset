# Fine-Tuning MobileNet on Food-101 Dataset

## Overview
This project fine-tunes the MobileNetV2 model pretrained on ImageNet to classify images from the Food-101 dataset. The entire workflow is implemented in Python using TensorFlow and can be executed on Google Colab.

## How to Run
Follow these steps to run the project on Google Colab:

1. **Launch Google Colab**
   - Open [Google Colab](https://colab.research.google.com/).
2. **Clone or Download the Repository**
   - Download the repository and upload the project files to your Google Drive.

3. **Upload the Notebook**
   - Upload the provided `.ipynb` notebook file to Colab.

4. **Mount Google Drive**
   - Ensure that the notebook mounts your Google Drive to access the dataset and save the model checkpoints. Add the following code snippet in the first cell if not already provided:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     ```

5. **Dataset Setup**
   - Download the Food-101 dataset from Kaggle. Use the following commands in Colab to download and extract:
     ```bash
     !kaggle datasets download dansbecker/food-101
     !unzip -o /content/food-101.zip > /dev/null
     ```

6. **Install Required Libraries**
   - Ensure all dependencies are installed by running:
     ```bash
     !pip install tensorflow matplotlib pandas seaborn
     ```

7. **Run the Notebook**
   - Execute each cell sequentially. The notebook handles:
     - Data preprocessing
     - Loading and fine-tuning the MobileNetV2 model
     - Training and saving the model

8. **Model Checkpoints**
   - Trained model checkpoints are saved in the specified directory within Google Drive.

## Checkpoints Description
   - **Checkpoint-1:** Model trained for 20 epochs with an initial learning rate of 0.001. Used as a baseline for further fine-tuning. (Mobilenet Freezed)
   - **Checkpoint-2:** Model fine-tuned for 5 additional epochs with a reduced learning rate of 0.0001 for better accuracy. (Layers Freezed after the 100th layer)
   - **Checkpoint-3:** Final model saved after training with early stopping and data augmentation, achieving optimal validation accuracy. (Lower Learning Rate)
   - 

## Evaluate Results
   - Evaluation metrics such as confusion matrix and accuracy plots are generated in the notebook.

## Notes
- Ensure that the Kaggle API key is set up for downloading the dataset.
- If using a free Colab session, monitor runtime limitations.

## Output Files
- Fine-tuned model checkpoint files (`.h5`).
- Plots for accuracy and loss over epochs.

---
This project demonstrates transfer learning with MobileNetV2 for image classification using the Food-101 dataset.
