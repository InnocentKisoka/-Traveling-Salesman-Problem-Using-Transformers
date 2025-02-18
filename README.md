# Traveling Salesman Problem Using Transformers

📌 Project Overview

The Traveling Salesman Problem (TSP) is a fundamental optimization challenge in computer science and mathematics. It involves finding the shortest possible route for a salesman to visit a given set of cities exactly once and return to the starting point. Due to its NP-hard complexity, heuristic and approximation methods play a crucial role in finding near-optimal solutions efficiently.
In this project, we explore a Transformer-based heuristic for solving TSP. While Transformers were initially designed for Natural Language Processing (NLP) tasks, they have demonstrated strong generalization capabilities across different domains, including combinatorial optimization.


🎯 Objectives

Encode TSP instances in a format suitable for Transformers.
Implement a Transformer-based heuristic model to approximate solutions.
Compare performance against random tours and greedy algorithms.
Evaluate the gap between heuristic solutions and the optimal tour.
Analyze model generalization for larger graphs and different problem variations.



📊 Dataset

We use the dataset from Joshi et al. (2020), which provides Euclidean TSP instances generated by randomly sampling points from a uniform distribution in the unit square.
The dataset includes:
Training, validation, and test splits with n = 20 nodes.
A dummy dataset for preliminary testing.


📌 Data Representation
Node coordinates (X): Tensor of size (20 × 2).
Tour labels (y): The shortest tour sequence starting and ending at node 0.
Edge attributes: Tour connections and corresponding weights.


🔥 Model Architecture

We implement a Transformer-based model adapted for TSP:
Transformer Encoder: Processes node embeddings.
Transformer Decoder: Generates the tour sequence.
Feed-Forward Neural Network (FFN): Processes output embeddings for final predictions.



🔑 Key Design Considerations

Masking: Applied to prevent invalid node visits.
Positional Encoding: Used in the decoder but omitted in the encoder.

🚀 Training Strategy

Training Transformers for combinatorial optimization is challenging. We implement:

Standard Training
Train the model for 10 minutes (or any feasible time budget).
Monitor training & validation loss to prevent overfitting.

Training with Gradient Accumulation
Adjusts batch processing to improve training stability.
Compare results with standard training.


📈 Evaluation

I evaluated the Transformer heuristic by comparing it to two baseline methods:
Random Tour: Generates a random route.
Greedy Algorithm: Iteratively selects the closest unvisited node.
Performance is measured using the optimality gap:


gap= (Approx−OPT)/OPT
​	
 
🔎 Analysis

Plot boxplots comparing solution quality across different models.
Assess generalization to larger graphs (e.g., n = 30 or 100).

📌 Model Limitations

Scalability to larger graphs.

Data limitations (fixed-size input).
Architectural constraints (e.g., handling non-Euclidean graphs).

📜 References

Joshi et al. (2020) – "Learning the Traveling Salesman Problem Requires Rethinking Generalization".
Vaswani et al. (2017) – "Attention is All You Need".
