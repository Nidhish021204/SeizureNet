# SeizuGraph: Dynamic Graph Neural Networks for EEG-Based Seizure Detection

## Project Overview

SeizuGraph is a deep learning framework built to detect and classify epileptic seizures using EEG (Electroencephalography) signals. By modeling brain activity as a dynamic graph and applying Graph Neural Networks (GNNs), this system captures rich spatio-temporal, semantic, and taxonomic relationships between brain regions to enhance diagnostic accuracy.

This project is inspired by research in neuroinformatics and brain signal modeling, and aims to support early and accurate seizure prediction for healthcare applications.

## Key Features

- EEG Signal Processing: Converts raw EEG data into structured graph representations based on electrode spatial configurations.
- Dynamic Graph Modeling: Captures time-series brain connectivity as evolving graphs to model both short-term and long-term patterns.
- Graph Neural Network Architectures: Implements GCN, GAT, and other GNN variants to learn meaningful features from brain graphs.
- Seizure Classification: Binary or multi-class seizure classification with high performance metrics.
- Custom Visualization Tools: Includes visualization of EEG connectivity graphs and model predictions.

## Project Structure

```
SeizuGraph/
├── data/                   # EEG datasets or link to CHB-MIT dataset  
├── preprocessing/          # Signal preprocessing scripts  
├── models/                 # GNN architectures - GCN, GAT, etc.  
├── utils/                  # Helper functions - metrics, visualization  
├── notebooks/              # Jupyter Notebooks for analysis and experiments  
├── main.py                 # Training/Testing pipeline  
├── requirements.txt        # Python dependencies  
└── README.md               # Project documentation
```

## Dataset

This project can be used with publicly available EEG datasets such as:

- CHB-MIT Scalp EEG Database: https://physionet.org/content/chbmit/1.0.0/
- Temple University Hospital (TUH) EEG Corpus: https://www.isip.piconepress.com/projects/tuh_eeg/

Data is preprocessed into segments and converted into graphs using spatial adjacency of EEG electrodes.

## Methodology

1. EEG Preprocessing: Filter, normalize, and segment raw EEG signals.  
2. Graph Construction: Construct brain connectivity graphs using spatial and statistical correlations.  
3. Dynamic Graph Creation: Model EEG windows as sequences of graph snapshots.  
4. GNN Training: Train GNNs to classify seizure vs. non-seizure activity.  
5. Evaluation: Use metrics such as Accuracy, F1-Score, Precision, and Recall.

## Results

| Model       | Accuracy | F1 Score | AUC  |
|-------------|----------|----------|------|
| GCN         | 87.3%    | 0.86     | 0.90 |
| GAT         | 89.1%    | 0.88     | 0.92 |
| GraphSAGE   | 88.6%    | 0.87     | 0.91 |

(Note: Performance depends on dataset and preprocessing pipeline.)

## Installation

Step 1: Clone the repository  
```bash
git clone https://github.com/nidhish-chttri/SeizuGraph.git
```

Step 2: Navigate into the project directory  
```bash
cd SeizuGraph
```

Step 3: Install the dependencies  
```bash
pip install -r requirements.txt
```

## Running the Project

To run the project, use the following command:  
```bash
python main.py --model GAT --dataset chbmit --epochs 50
```

You can modify model architecture, dataset path, and hyperparameters in the `config.py` file or through the command line.

## Visualization Example

To visualize a brain connectivity graph, use the following function:  
```python
from utils.visualization import plot_brain_graph  
plot_brain_graph(graph_data)
```

## Author

**Nidhish Chettri**  
B.Tech, Maharaja Agrasen Institute of Technology, Delhi  
- LinkedIn: https://linkedin.com/in/nidhish-chettri  
- GitHub: https://github.com/nidhish-chttri

## License

This project is open-sourced under the MIT License. See the LICENSE file for details.

## Acknowledgments

- Inspired by NeuroGNN (USC InfoLab): https://github.com/USC-InfoLab/NeuroGNN  
- EEG data sourced from PhysioNet: https://physionet.org/  
- GNN implementations inspired by PyTorch Geometric: https://pytorch-geometric.readthedocs.io/