

# Molecular Joint Representation Learning via Multi-Modal Information of SMILES and Graphs

## Summary

This paper proposes a novel framework called MMSG (Multi-Modal SMILES and Graphs) for molecular representation learning that combines information from both SMILES strings and molecular graphs. The key contributions are:

1. Introducing bond-level graph representations as attention bias in Transformer to reinforce feature correspondence between SMILES and graph modalities.

2. Proposing a Bidirectional Message Communication Graph Neural Network (BMC GNN) to strengthen information flow in graph representations.

3. Achieving state-of-the-art results on multiple benchmark datasets for molecular property prediction tasks.

## Key Concepts

### Multi-Modal Molecular Representation

The MMSG framework leverages both SMILES strings and molecular graphs as input modalities:

- SMILES: Linear text representation of molecules
- Graphs: Represent molecular structure as nodes (atoms) and edges (bonds)

By combining these, MMSG aims to capture both global molecular information and local structural details.

### Transformer with Graph-Enhanced Attention

The authors modify the self-attention mechanism in Transformer by incorporating bond-level graph information as an attention bias. This helps the model better capture hidden bond information in SMILES strings.

### Bidirectional Message Communication GNN 

The BMC GNN improves upon previous message passing neural networks by enabling bidirectional communication between atom and bond representations in the molecular graph.

## Architecture

![MMSG Architecture](images\figure1.png)

Figure 2 shows the overall MMSG architecture:

1. SMILES and graph representations are projected into matrices
2. The upper stack processes SMILES using GRU and Transformer 
3. The lower stack processes graphs using the BMC GNN
4. Bond representations are introduced into the Transformer as attention bias
5. Final embeddings are concatenated for property prediction

## Results

The MMSG framework outperforms state-of-the-art baselines on multiple benchmark datasets:

| Dataset | Task Type | Performance Metric |
|---------|-----------|---------------------|
| BBBP    | Classification | ROC-AUC |
| Tox21   | Classification | ROC-AUC |
| SIDER   | Classification | ROC-AUC |
| ClinTox | Classification | ROC-AUC |
| FreeSolv | Regression | RMSE |
| ESOL    | Regression | RMSE |
| Lipophilicity | Regression | RMSE |

Table 6 shows detailed results comparing MMSG to baseline models on scaffold splitting. MMSG achieves the best performance across all datasets.

## Visualizations

![Latent Space Visualization](images\figure4.png)

Figures 4-6 visualize the latent space learned by different models using UMAP. MMSG (c) shows more nuanced clustering of molecules compared to Transformer (a) and CMPNN (b), suggesting it captures more comprehensive molecular representations.

## Conclusion

The MMSG framework demonstrates the potential of combining multiple molecular representations to improve property prediction tasks. By leveraging both SMILES and graph information, it achieves state-of-the-art performance across various benchmarks.