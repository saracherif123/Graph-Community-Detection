# Community Detection and Evaluation

**Authors:** Stephanie Gomes and Sara Saad 

## Overview

This project performs community detection and evaluation on two real-world network datasets: Wikipedia Voting Network and Facebook Social Circles. The analysis includes graph statistics, centrality measures, community detection algorithms, and quality evaluation metrics.

## Datasets

### Wikipedia Voting Network
- **Source:** [SNAP - Wiki-Vote](https://snap.stanford.edu/data/wiki-Vote.html)
- **Nodes:** 7,115 users
- **Edges:** 103,689 votes (directed)
- **Description:** Represents votes cast by users on others in Wikipedia administrator elections

### Facebook Social Circles
- **Source:** [SNAP - ego-Facebook](https://snap.stanford.edu/data/ego-Facebook.html)
- **Nodes:** 4,039 users
- **Edges:** 88,234 friendships (undirected)
- **Description:** Represents friendship connections in a Facebook social network

## Installation

1. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Project Structure

```
.
├── Saad_Gomes.ipynb          # Main analysis notebook
├── wikepedia_vote_dataset/
│   └── Wiki-Vote.txt         # Wikipedia voting dataset
└── facebook_dataset/
    └── facebook_combined.txt  # Facebook social network dataset
```

## Analysis Components

### 1. Graph Analysis
- Degree distribution
- Centrality measures (betweenness, closeness, eigenvector, PageRank)
- Clustering coefficient
- Network statistics (diameter, density, path length)

### 2. Community Detection Algorithms
- **Louvain Method:** Optimizes modularity for finding dense communities
- **Walktrap Algorithm:** Uses random walks to identify communities at multiple resolutions

### 3. Evaluation Metrics
- **Modularity:** Measures internal vs. external edge density
- **Conductance:** Assesses community separability
- **Cut Ratio:** Measures external connectivity

## Key Findings

### Wikipedia Voting Network
- **Louvain:** 29 communities, modularity 0.4243, conductance 0.0697
- **Walktrap:** 2,365 communities, modularity 0.3748, conductance 0.9862
- Louvain finds larger, more cohesive communities; Walktrap identifies fine-grained micro-communities

### Facebook Social Circles
- **Louvain:** 15 communities, modularity 0.8349, conductance 0.0465, cut ratio 0.0005
- **Walktrap:** 77 communities, modularity 0.8119, conductance 0.2506, cut ratio 0.0006
- Strong small-world properties (diameter: 8, avg path length: 3.69)
- High clustering coefficient (0.6055) indicating strong local connectivity
- Network density: 1.0820% with 1,612,010 triangles
- Louvain finds fewer but larger, highly cohesive communities with excellent modularity; Walktrap identifies more fine-grained communities

## Usage

Open and run the Jupyter notebook `Saad_Gomes.ipynb` to execute the complete analysis. The notebook is organized into sections for each dataset, including analysis, community detection, and evaluation.



