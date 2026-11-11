🧮 Cosine Similarity
Understanding Vector Similarity & Textual Similarity with Python

<p align="center">
<img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/NumPy-Scientific%20Computing-013243?style=for-the-badge&logo=numpy&logoColor=white" />
<img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white" />
<img src="https://img.shields.io/badge/Jupyter-Notebooks-F37626?style=for-the-badge&logo=jupyter&logoColor=white" />
<img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" />
</p>

<p align="center">
<b>A practical exploration of Cosine Similarity — from mathematical fundamentals to real-world text similarity applications.</b>
</p>

📌 Overview

Cosine Similarity is a hands-on Python project that explores how mathematical vectors can be used to measure similarity between different objects, numerical representations, and textual documents.

This repository demonstrates the implementation of cosine similarity from scratch using NumPy, compares it with established scientific Python libraries, and explores how the technique can be applied to textual data.

Whether you're learning linear algebra, exploring machine learning, or developing an understanding of Natural Language Processing (NLP), this project provides an intuitive starting point.

✨ What You'll Explore
Mathematical Foundations: Understand dot products, vector magnitudes, and the angle between vectors.
Implementation from Scratch: Calculate cosine similarity using NumPy without relying on a pre-built similarity function.
Library Comparison: Compare custom calculations with Scikit-learn and SciPy implementations.
Cosine Distance: Understand the relationship between cosine similarity and cosine distance.
Text Similarity: Explore how documents can be represented as numerical feature vectors.
Document Comparison: Calculate pairwise similarity between multiple documents.
3D Visualization: Visualize vectors geometrically to develop an intuition for similarity.
🧠 Understanding Cosine Similarity

Cosine Similarity measures how similar two vectors are by calculating the cosine of the angle between them.

Unlike distance-based measurements, it focuses on the orientation of vectors rather than their magnitude.

Mathematical Formula

For two vectors 
𝐴
 and 
𝐵
:

Cosine Similarity
(
𝐴
,
𝐵
)
=
𝐴
⋅
𝐵
∥
𝐴
∥
∥
𝐵
∥

Where:

𝐴
⋅
𝐵
 represents the dot product of the vectors.
∥
𝐴
∥
 represents the magnitude (Euclidean norm) of vector A.
∥
𝐵
∥
 represents the magnitude (Euclidean norm) of vector B.
Interpreting the Results
Similarity Score	Interpretation
1.0	Identical direction
0.8 – 0.99	Highly similar direction
0.5 – 0.79	Moderately similar direction
0.0	Perpendicular vectors
-1.0	Opposite direction

Note: These ranges are illustrative, not universal classification thresholds. For non-negative feature vectors, such as term-frequency vectors, cosine similarity typically falls between 0 and 1.

Cosine Similarity vs. Cosine Distance

Cosine distance measures dissimilarity using:

Cosine Distance
=
1
−
Cosine Similarity

A smaller cosine distance indicates greater directional similarity.

📂 Project Structure
text
Cosine-Similarity/
│
├── Basic_working.ipynb
│   └── Mathematical implementation and
│       visualization of cosine similarity
│
├── STRINGcosine_similarity.ipynb
│   └── Applying cosine similarity to
│       numerical representations of text
│
├── LICENSE
│
└── README.md

📓 Notebooks Explained
1. Basic Working — Basic_working.ipynb

This notebook explores the mathematical working of cosine similarity using numerical vectors.

Topics covered:

Creating numerical vectors using NumPy.
Calculating dot products.
Computing vector magnitudes using numpy.linalg.norm().
Implementing cosine similarity manually.
Comparing results with Scikit-learn.
Calculating cosine distance using SciPy.
Visualizing vectors in three-dimensional space using Matplotlib.

Example:

python
import numpy as np
from sklearn.metrics.pairwise import cosine_similarity

# Define two vectors
vec1 = np.array([1, 2, 3])
vec2 = np.array([1, 2, 1])

# Calculate dot product
dot_product = np.dot(vec1, vec2)

# Calculate magnitudes
mag_1 = np.linalg.norm(vec1)
mag_2 = np.linalg.norm(vec2)

# Calculate cosine similarity manually
similarity = dot_product / (mag_1 * mag_2)

print("NumPy Similarity:", similarity)

# Verify using Scikit-learn
sklearn_similarity = cosine_similarity(
    vec1.reshape(1, -1),
    vec2.reshape(1, -1)
)

print("Scikit-learn Similarity:", sklearn_similarity[0][0])


Expected Output:

text
NumPy Similarity: 0.8728715609439697
Scikit-learn Similarity: 0.8728715609439697

2. String Cosine Similarity — STRINGcosine_similarity.ipynb

This notebook explores the application of cosine similarity to textual documents.

It demonstrates how text documents can be represented using numerical feature vectors and how these representations can be compared to determine their similarity.

Topics covered:

Understanding text representation through numerical features.
Working with sample documents about iPhone and Samsung Galaxy.
Creating a Pandas DataFrame containing word-frequency features.
Calculating similarity between individual documents.
Generating a pairwise document similarity matrix.
Exploring cosine distance using Scikit-learn.

Example:

python
import pandas as pd
from sklearn.metrics.pairwise import cosine_similarity

# Numerical representation of documents
df = pd.DataFrame(
    [
        {'iPhone': 3, 'galaxy': 1},
        {'iPhone': 2, 'galaxy': 0},
        {'iPhone': 1, 'galaxy': 3},
        {'iPhone': 1, 'galaxy': 2}
    ],
    index=['doc1', 'doc2', 'doc3', 'doc4']
)

# Calculate pairwise similarity
similarity_matrix = cosine_similarity(df)

print(similarity_matrix)


What happens here?

Each document is represented as a vector of numerical features. Scikit-learn then calculates the cosine similarity between every pair of document vectors.

The resulting matrix helps identify which documents have similar feature distributions.

Note: The notebook uses manually constructed numerical features rather than an automated text-vectorization pipeline.

⚙️ Installation & Setup
Prerequisites

Make sure you have the following installed:

Python 3.x
Jupyter Notebook or JupyterLab
pip package manager
1. Clone the Repository
bash
git clone https://github.com/Mr-Special/Cosine-Similarity.git

2. Navigate to the Project Directory
bash
cd Cosine-Similarity

3. Install Dependencies
bash
pip install numpy pandas scipy scikit-learn matplotlib jupyter

4. Launch Jupyter Notebook
bash
jupyter notebook


Open either notebook and execute the cells sequentially.

Alternative: Google Colab

You can also explore the notebooks directly in Google Colab without configuring a local Python environment.

Open Basic Working in Google Colab
Open String Cosine Similarity in Google Colab
🛠️ Technologies Used
Technology	Purpose
Python	Core programming language
NumPy	Vector operations and mathematical calculations
Pandas	Data manipulation and document representation
SciPy	Cosine distance calculations
Scikit-learn	Cosine similarity and pairwise comparisons
Matplotlib	Three-dimensional vector visualization
Jupyter Notebook	Interactive experimentation and learning
🌍 Real-World Applications

Cosine similarity is widely used in machine learning, information retrieval, and data analysis.

Some notable applications include:

Search Engines: Measuring similarity between search queries and indexed documents.
Recommendation Systems: Finding products, movies, or items with similar feature representations.
Natural Language Processing: Comparing numerical representations of textual documents.
Document Clustering: Identifying groups of documents with similar characteristics.
Plagiarism Detection: Identifying potentially similar textual content.
Information Retrieval: Ranking documents based on their similarity to a query.
Semantic Search: Comparing vector embeddings to retrieve conceptually related information.
⚠️ Important Considerations
Both vectors must have the same number of dimensions.
Cosine similarity is undefined when either vector has zero magnitude.
Similarity scores depend on how the input data is represented.
Similarity between text documents does not automatically imply semantic equivalence.
Feature engineering and text preprocessing can significantly influence the results.
🚀 Future Improvements

Potential directions for extending this project include:

Implement automated text preprocessing and tokenization.
Explore Bag of Words and TF-IDF vectorization.
Compare cosine similarity with Euclidean distance.
Experiment with sentence and document embeddings.
Build a simple document similarity search engine.
Visualize similarity matrices using heatmaps.
Explore semantic similarity using transformer-based models.
🤝 Contributing

Contributions, suggestions, and improvements are welcome!

If you would like to contribute:

Fork this repository.
Create a new branch.
bash
git checkout -b feature/your-feature-name

Make your changes.
Commit your changes.
bash
git commit -m "Add: your contribution"

Push your branch.
bash
git push origin feature/your-feature-name

Open a Pull Request.
📜 License

This project is distributed under the MIT License.

You are free to use, modify, and distribute the project in accordance with the license terms.

See the LICENSE file for more information.

👨‍💻 Author

Mr-Special

GitHub: @Mr-Special

Repository: Cosine-Similarity

<p align="center">
<b>⭐ If you find this project useful, consider giving it a star!</b>
<br/>
<sub>Explore. Experiment. Understand the mathematics behind similarity.</sub>
</p>
