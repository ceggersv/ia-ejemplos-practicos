# Word Embeddings Visualization Tool

![Word Embeddings](https://img.shields.io/badge/NLP-Word%20Embeddings-blue)
![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-brightgreen)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

A simple, educational tool for visualizing word embeddings in 2D space using pre-trained GloVe models. This project demonstrates how word vectors capture semantic relationships between words and can be used for teaching the concepts of word embeddings.

## 📋 Overview

This project provides a Jupyter notebook that:

- Loads pre-trained GloVe word embeddings (Twitter-200d)
- Projects high-dimensional word vectors to 2D space using PCA
- Visualizes selected words in a 2D plot
- Demonstrates vector relationships (e.g., king - man + woman ≈ queen)
- Calculates cosine similarities between words

Perfect for educational purposes to introduce natural language processing concepts and word embeddings to students or colleagues.

## 🔍 Example Visualization

The notebook generates visualizations showing how words like 'king', 'queen', 'man', 'woman', 'child', 'throne', 'crown', and 'royalty' relate to each other in vector space.

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or Google Colab

### Installation

1. Clone this repository:
   ```
   git clone https://github.com/your-username/word-embeddings-visualization.git
   cd word-embeddings-visualization
   ```

2. Install required packages:
   ```
   pip install -r requirements.txt
   ```

3. Launch Jupyter Notebook:
   ```
   jupyter notebook
   ```

4. Open `Word_Embeddings_Visualization.ipynb`

### Using Google Colab

Alternatively, you can run this notebook in Google Colab:

1. Open [Google Colab](https://colab.research.google.com/)
2. Select `File > Upload notebook` and choose the notebook file
3. Run the cells in order

## 📊 Usage

1. The default example visualizes these words:
   ```python
   words = ['king', 'queen', 'man', 'woman', 'child', 'throne', 'crown', 'royalty']
   ```

2. Customize the list to include your own words:
   ```python
   words = ['your', 'custom', 'word', 'list']
   ```

3. You can also change the pre-trained model:
   ```python
   # Default model
   glove_twitter = api.load("glove-twitter-200")
   
   # Alternative models
   # glove_wiki = api.load("glove-wiki-gigaword-300")
   # word2vec_google = api.load("word2vec-google-news-300")
   ```

## 🔧 Features

- **2D Visualization**: PCA dimensionality reduction to visualize high-dimensional embeddings
- **Relationship Analysis**: Vectors connecting related words (e.g., gender relationships)
- **Vector Arithmetic**: Demonstrates the algebraic properties of word embeddings
- **Similarity Metrics**: Calculates and displays cosine similarities between words

## 🎓 Educational Uses

This notebook is ideal for:

- Introducing NLP concepts to students
- Workshops on word embeddings
- Visualizing semantic relationships between words
- Demonstrating vector arithmetic in language models

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📚 References

- [GloVe: Global Vectors for Word Representation](https://nlp.stanford.edu/projects/glove/)
- [Word2Vec: Efficient Estimation of Word Representations in Vector Space](https://arxiv.org/abs/1301.3781)
- [Gensim: Topic modelling for humans](https://radimrehurek.com/gensim/)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---

Created for educational purposes to demonstrate word embedding concepts in a visual, intuitive way.
