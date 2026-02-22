# Community Detection and Graph Embeddings

**Authors:** Stephanie Gomes and Sara Saad

Analysis of real-world networks: community detection, centrality, shallow embeddings (Node2Vec, DeepWalk), and GNNs (GCN, GraphSAGE, GAT).

---

## Datasets

| Dataset | Nodes | Edges | Type | Path |
|---------|-------|-------|------|------|
| **Wiki-Vote** | 7,115 | 103,689 | Directed | `wikepedia_vote_dataset/Wiki-Vote.txt` |
| **Facebook** | 4,039 | 88,234 | Undirected | `facebook_dataset/facebook_combined.txt` |

Sources: [SNAP Wiki-Vote](https://snap.stanford.edu/data/wiki-Vote.html), [SNAP ego-Facebook](https://snap.stanford.edu/data/ego-Facebook.html)

---

## Notebooks

| Notebook | Dataset(s) | Contents |
|----------|------------|----------|
| **Saad_Gomes_First_Deliver.ipynb** | Wiki-Vote, Facebook | Graph stats, centrality (betweenness, closeness, eigenvector, PageRank), Louvain & Walktrap, modularity/conductance/cut-ratio |
| **Saad_Gomes_Final_Deliver.ipynb** | Wiki-Vote, Facebook | Final deliver file merging notebooks |
| **GNNs.ipynb** | Facebook | Node2Vec, DeepWalk, GCN, GraphSAGE, GAT, link prediction, t-SNE visualization |
| **wiki_vote_embeddings_gnn.ipynb** | Wiki-Vote | Shallow embeddings, GNNs for node classification |

---

## Setup

```bash
python3.12 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt --extra-index-url https://download.pytorch.org/whl/cpu
```

Requires Python 3.10–3.12 (gensim incompatible with 3.13).

---

## Project Structure

```
├── Saad_Gomes_First_Deliver.ipynb              # Community detection
├── Saad_Gomes_Final_Deliver.ipynb              # Presentation
├── wiki_vote_embeddings_gnn.ipynb
├── GNNs.ipynb
├── wikepedia_vote_dataset/
│   └── Wiki-Vote.txt
├── facebook_dataset/
│   └── facebook_combined.txt
└── requirements.txt
```

---

## Key Results

**Wiki-Vote:** Louvain 30 communities (mod 0.42), Walktrap 2,365 (mod 0.37). Node 2565 top in all centralities.

**Facebook:** Louvain 15 communities (mod 0.83), Walktrap 77 (mod 0.81). Diameter 8, clustering 0.60. Node 107 highest betweenness/closeness; Node 3437 highest PageRank.

---

## Run

```bash
jupyter notebook
# Open desired .ipynb and run cells sequentially
```
