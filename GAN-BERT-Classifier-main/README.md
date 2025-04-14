# GAN-BERT Text Classifier

A semi-supervised text classification project based on BERT and Generative Adversarial Networks (GAN). This project combines the powerful text representation capabilities of BERT with the semi-supervised learning capabilities of GAN, making it particularly suitable for scenarios with limited labeled data.

## Features

- Combines BERT and GAN advantages for text classification
- Supports semi-supervised learning, utilizing both labeled and unlabeled data
- Provides support for multiple datasets (sentiment analysis, letter classification, etc.)
- Supports GPU-accelerated training
- Includes comprehensive model evaluation and visualization tools

## Project Structure

```
GAN-BERT-Classifier-main/
├── data/                    # Dataset directory
│   ├── sentiment/          # Sentiment analysis dataset
│   ├── letters/            # Letter classification dataset
│   └── news/               # News classification dataset
├── results/                # Results output directory
├── ganbert.py             # GAN-BERT model core implementation
├── main.py                # Project entry file
└── BERT_Text_Classification.ipynb  # Experiment and visualization notebook
```

## Requirements

- Python 3.8+
- PyTorch
- Transformers
- pandas
- numpy
- scikit-learn
- matplotlib

## Installation

```bash
pip install transformers
pip install torch
pip install pandas numpy scikit-learn matplotlib
```

## Usage

1. Prepare Data
   - Place data files in the `data` directory
   - Supports JSON format input data
   - Data format example:
     ```json
     {
       "text": "text content",
       "author": "author label"
     }
     ```

2. Train Model
   ```bash
   python main.py --training data/letters/classification/classifier_data_train.json \
                 --input data/letters/classification/classifier_data_eval.json \
                 --output results/results_GANBERT.txt \
                 --text_label text \
                 --label author
   ```

3. Parameter Description
   - `--training`: Path to training data file
   - `--input`: Path to evaluation data file
   - `--output`: Path to results output file
   - `--text_label`: Text field name
   - `--label`: Label field name

## Model Architecture

### Generator
- Input: Noise vector (dimension: 100)
- Output: Text representation (dimension: 512)
- Uses multi-layer neural network to generate text representations

### Discriminator
- Input: Text representation
- Output: Class prediction and real/fake judgment
- Includes multi-layer neural network and softmax classification

### GAN-BERT Model
- Combines advantages of BERT and GAN
- Supports semi-supervised learning
- Can handle both labeled and unlabeled data

## Experimental Results

Based on project results:
- Training data: 38,295 unlabeled samples, 782 labeled samples
- Test data: 4,881 samples
- Classification categories: 7 different classes
- Model effectively handles author classification task

## Notes

1. Data Preparation
   - Ensure correct data format
   - Recommended to preprocess and clean data

2. Training Process
   - Recommended to use GPU for training
   - Model performance can be optimized by adjusting parameters
   - Monitor loss value changes during training

3. Model Evaluation
   - Uses confusion matrix for performance evaluation
   - Classification effects can be optimized by adjusting thresholds

## Contributing

Welcome to submit issues and improvement suggestions! If you want to contribute code:

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## Contact

For any questions or suggestions, please contact:
- Submit an Issue
- Send email to [your-email@example.com]

## Acknowledgments

Thanks to all developers who contributed to this project! 