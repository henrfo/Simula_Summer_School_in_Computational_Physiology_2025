# Sparse Distributed Memory Model Implementation for MNIST

This repository contains an implementation of Kanerva's Sparse Distributed Memory (SDM) model applied to MNIST digit recognition, developed for the Simula Summer School in Computational Physiology 2025.

## Overview

This project explores Kanerva's Sparse Distributed Memory as a biologically-inspired neural memory model, comparing it with traditional approaches like Hopfield networks. The implementation demonstrates how SDM preserves the uniqueness of patterns while maintaining robust retrieval capabilities, similar to how the hippocampus processes episodic memories.

## Project Structure

```
├── kanerva_sdm_mnist_henrik.ipynb    # Main implementation notebook
├── presentation-script_final.md      # Detailed presentation notes
├── SSCP2025 presentation.pdf        # Final presentation slides
├── sscp_project_2025.pdf           # Project documentation
├── articles/                        # Research papers and references
│   ├── KanervaP_SDMrelated_models1993.pdf
│   ├── hopfield_1982.pdf
│   ├── hopfield_is_all_you_need.pdf
│   └── ...
└── pkl/                            # Cached model files (not tracked)
```

## Key Features

- **MNIST Implementation**: Complete SDM implementation for digit recognition
- **Noise Robustness Analysis**: Comprehensive testing of model performance under various noise conditions
- **Capacity Analysis**: Investigation of memory capacity limits and performance scaling
- **Visualization Tools**: t-SNE embeddings and clustering analysis of hyperdimensional representations
- **Comparative Study**: Analysis against traditional neural memory models

## Model Architecture

The implementation follows this pipeline:
1. **Input Processing**: MNIST digits (28×28) → Binary thresholding → Bipolar representation (+1/-1)
2. **Hyperdimensional Encoding**: Project to 2000-dimensional space using basis vectors
3. **Sparse Activation**: Activate only 0.5% (500 of 100,000) memory locations
4. **Associative Retrieval**: Pattern completion from partial or noisy cues

## Key Results

- **Accuracy**: 70.9% on clean MNIST test images
- **Noise Robustness**: Graceful degradation under increasing noise levels
- **Memory Capacity**: Maintains performance from hundreds to 25,000+ stored patterns
- **Biological Relevance**: Demonstrates hippocampus-like preservation of pattern uniqueness

## Installation and Setup

```bash
# Clone the repository
git clone [repository-url]
cd Simula_Summer_School_in_Computational_Physiology_2025

# Create conda environment
conda env create -f environment.yml
conda activate sscp

# Install additional dependencies
pip install torch torchvision torchhd umap-learn matplotlib numpy scikit-learn
```

## Usage

The main implementation is contained in `kanerva_sdm_mnist_henrik.ipynb`. The notebook includes:

1. **Data Loading**: MNIST dataset preprocessing and hyperdimensional encoding
2. **Model Training**: SDM initialization and training on MNIST digits
3. **Evaluation**: Performance testing on clean and noisy images
4. **Analysis**: Comprehensive robustness and capacity analysis
5. **Visualization**: t-SNE embeddings of hyperdimensional representations

Run the notebook cells sequentially to reproduce all results and visualizations.

## Research Context

This project was developed for the Simula Summer School in Computational Physiology 2025, exploring the intersection of neuroscience and artificial intelligence. The work investigates:

- **Memory Models**: Comparison between Hopfield networks and Sparse Distributed Memory
- **Biological Inspiration**: How SDM mirrors hippocampal memory processing
- **Computational Efficiency**: Sparse representations for large-scale pattern storage
- **Noise Robustness**: Graceful degradation vs. catastrophic failure in neural memories

## Key References

- Kanerva, P. (1993). Sparse distributed memory and related models
- Hopfield, J.J. (1982). Neural networks and physical systems with emergent collective computational abilities
- Rolls, E.T. (2013). The mechanisms for pattern completion and pattern separation in the hippocampus
- Modern implementations and applications of hyperdimensional computing

## Contributing

This is a research project developed for educational purposes. Feel free to explore the code, adapt the implementation, or extend the analysis for your own research.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Developed by Henrik Formoe for the Simula Summer School in Computational Physiology 2025.

## Acknowledgments

- Simula Summer School in Computational Physiology 2025 organizers & Simula Research Laboratory
- University of Oslo (UiO)
- University of California, San Diego (UCSD)
- Research community working on hyperdimensional computing and neural memory models
- PyTorch and TorchHD teams - this student project was made possible by their excellent tools
