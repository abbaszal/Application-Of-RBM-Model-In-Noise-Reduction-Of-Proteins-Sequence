

# Application of RBM Model in Noise Reduction of Protein Sequences

## Overview

This project explores the application of Restricted Boltzmann Machines (RBMs) in the noise reduction of protein sequences. The RBM, a generative model from machine learning, is used to learn the underlying distribution of protein sequence data. The primary goal is to denoise the data by leveraging the model's ability to generate "fantasy" data that ideally represents the original, noise-free sequences. The project compares the effectiveness of different activation functions and analyzes the impact of various parameters on the model's performance.

## Project Structure

### 1. **Abstract**
   - The project focuses on using RBMs to denoise a binary dataset representing protein sequences. Two types of activation functions are tested: cell-by-cell and structure-preserving. The effectiveness of the model is evaluated using a custom metric called the Percentage of Deformed Rows (PDR). The results indicate that the structure-preserving activation function significantly outperforms the cell-by-cell method.

### 2. **Introduction**
   - **Restricted Boltzmann Machines (RBMs)**: RBMs are generative models used to learn the distribution from which the training data is drawn. The model consists of a visible layer (data layer) and a hidden layer (latent features), with connections between the layers but not within them.
   - **Objective**: The main objective is to use RBMs for noise reduction in protein sequences, testing different activation functions and parameter settings to optimize the model's performance.

### 3. **Methods**
   - **Data Representation**: Protein sequences are encoded using a one-hot encoding method, resulting in an \(N \times 20\) matrix, where \(N\) is the number of sequences, and 20 corresponds to the main amino acid types.
   - **RBM Architecture**: Both visible and hidden layers are modeled as Bernoulli variables. The energy function of the system is defined, and the log-likelihood is maximized using Stochastic Gradient Descent (SGD).
   - **Activation Functions**:
     - **Cell-by-Cell Activation**: Updates each unit in the visible layer individually.
     - **Structure-Preserving Activation**: Maintains block structures within the data, providing the model with additional information about the allowed patterns in the sequences.
   - **Training Process**: The RBM is trained using Contrastive Divergence (CD) cycles, and both vanilla SGD and the ADAM optimizer are tested for updating the model parameters.

### 4. **Results**
   - **Visualization**: The project visualizes the trained RBM model and the generated fantasy data, showing how the model learns to represent the input data and reduces noise.
   - **Performance Metrics**: The Percentage of Deformed Rows (PDR) is introduced as a key metric to evaluate the model's performance. The PDR is the ratio of rows with deformed patterns to the total number of rows.
   - **Effect of Activation Functions**: The structure-preserving activation function significantly reduces the PDR compared to the cell-by-cell method, demonstrating the importance of encoding structural information in the model.
   - **Impact of Contrastive Divergence Cycles**: Increasing the number of CD cycles did not lead to significant performance improvements, suggesting that the chosen settings were already optimal for this task.
   - **Noise Resilience**: The RBM model remains effective even under high noise conditions, significantly reducing the PDR in the generated data.

### 5. **Conclusion**
   - The RBM model effectively reduces noise in protein sequence data, particularly when using a structure-preserving activation function. The results highlight the model's robustness and the importance of incorporating structural information during training. The project demonstrates the potential of RBMs in bioinformatics applications, particularly for tasks involving noisy data.



### Files
- `RBM_23_ADAM_loglikehood.ipynb`: The main notebook containing the implementation of the RBM model and the analysis.
- `_Application_Of_RBM_Model_In_Noise_Reduction_Of_Proteins.pdf`: A detailed report documenting the methodology, results, and conclusions.

## References
- Pankaj Mehta et al., "A high-bias, low-variance introduction to Machine Learning for physicists," Physics Reports, 2019.
- Li G, Du X, Li X, et al. "Prediction of DNA binding proteins using local features and long-term dependencies with primary sequences based on deep learning." PeerJ, 2021.
- Luo Y, Jiang J, Zhu J, et al. "A Caps-Ubi Model for Protein Ubiquitination Site Prediction." Front. Plant Sci., 2022.

## Acknowledgments

This project was developed by Group 19 as part of an exploration into the application of RBMs in bioinformatics. We would like to thank our contributors and the academic community for their support and insights.
