# Community Detection and Evaluation

**Authors:** Stephanie Gomes and Sara Saad 

## Overview

This project performs community detection and evaluation on two real-world network datasets: Wikipedia Voting Network and Facebook Social Circles. The analysis includes graph statistics, centrality measures, community detection algorithms, and quality evaluation metrics.

## Datasets

### Wikipedia Voting Network
- **Source:** [SNAP - Wiki-Vote](https://snap.stanford.edu/data/wiki-Vote.html)
- **Download Link:** [Wiki-Vote.txt](https://snap.stanford.edu/data/wiki-Vote.txt.gz)
- **Local Path:** `wikepedia_vote_dataset/Wiki-Vote.txt`
- **Nodes:** 7,115 users
- **Edges:** 103,689 votes (directed)
- **Description:** Represents votes cast by users on others in Wikipedia administrator elections
- **Format:** Each line contains two node IDs (FromNodeId ToNodeId), representing a directed edge

### Facebook Social Circles
- **Source:** [SNAP - ego-Facebook](https://snap.stanford.edu/data/ego-Facebook.html)
- **Download Link:** [ego-Facebook](https://snap.stanford.edu/data/ego-Facebook.txt.gz)
- **Local Path:** `facebook_dataset/facebook_combined.txt`
- **Nodes:** 4,039 users
- **Edges:** 88,234 friendships (undirected)
- **Description:** Represents friendship connections in a Facebook social network
- **Format:** Each line contains two node IDs (NodeId1 NodeId2), representing an undirected edge

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
- **Louvain:** 30 communities, modularity 0.4230, conductance 0.0890
- **Walktrap:** 2,365 communities, modularity 0.3748, conductance 0.9862
- Louvain finds larger, more cohesive communities; Walktrap identifies fine-grained micro-communities

### Facebook Social Circles
- **Louvain:** 15 communities, modularity 0.8349, conductance 0.0465, cut ratio 0.0005
- **Walktrap:** 77 communities, modularity 0.8119, conductance 0.2506, cut ratio 0.0006
- Strong small-world properties (diameter: 8, avg path length: 3.69)
- High clustering coefficient (0.6055) indicating strong local connectivity
- Network density: 1.0820% with 1,612,010 triangles
- Louvain finds fewer but larger, highly cohesive communities with excellent modularity; Walktrap identifies more fine-grained communities

## How to Use the Data

### Step 1: Download the Datasets

If the datasets are not already in the project directory, download them from the SNAP website:

1. **Wikipedia Voting Network:**
   ```bash
   wget https://snap.stanford.edu/data/wiki-Vote.txt.gz
   gunzip wiki-Vote.txt.gz
   mkdir -p wikepedia_vote_dataset
   mv wiki-Vote.txt wikepedia_vote_dataset/
   ```

2. **Facebook Social Circles:**
   ```bash
   wget https://snap.stanford.edu/data/ego-Facebook.txt.gz
   gunzip ego-Facebook.txt.gz
   mkdir -p facebook_dataset
   # Note: The notebook expects a combined format. If using the original SNAP data,
   # you may need to preprocess it to match the expected format.
   ```

### Step 2: Verify Data Location

Ensure the data files are in the correct locations:
- `wikepedia_vote_dataset/Wiki-Vote.txt` - Wikipedia voting network
- `facebook_dataset/facebook_combined.txt` - Facebook social network

### Step 3: Run the Notebook

1. **Activate the virtual environment:**
   ```bash
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

2. **Start Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

3. **Open and run `Saad_Gomes.ipynb`:**
   - The notebook is organized into sections for each dataset
   - All result cells are open and visible
   - Run cells sequentially from top to bottom
   - The notebook includes:
     - Graph loading and preprocessing
     - Graph statistics and visualization
     - Centrality measures
     - Community detection (Louvain and Walktrap)
     - Community evaluation metrics
     - Advanced analysis (Facebook dataset)

### Step 4: View Results

All analysis results are displayed in the notebook cells:
- Graph visualizations
- Statistical summaries
- Community detection results
- Evaluation metrics
- Comparison tables

**Note:** The notebook uses random seeds (42) for reproducibility. Running the cells will produce consistent results.



