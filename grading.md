**Apply appropriate data structures** 
 
- Memory-Conscious Design: 
Implement data structures that minimize memory footprint while preserving functionality.  
For example, image representation and model parameters (how to store weights / biases etc.). 

- Algorithm-Specific Structures: 
Create algorithm architecture in such way, that is saves memory while preserving functionality. 
For example, for Decision Trees: representation of tree nodes and for Neural Networks: weights implementation and batches setup. 

- Trade-Off Justification: 
Clearly explain in a report why chosen structures are optimal for the device constraints (256 KB RAM, 1 MB storage). Discusses alternatives and why they were rejected. 

- Code Quality: 
Structures are implemented cleanly, documented, and reusable. 
 
**Apply Algorithmic thinking**
 
- Algorithm Selection: 
Choose algorithms that balance accuracy and resource constraints. For example, choose lightweight classifiers (e.g., small Decision Tree, or shallow Neural Network) over heavy models. 

- Optimization Techniques: 
Implements quantization (e.g., reducing precision of weights and activations). 
Uses mini-batch training with ring buffers to reduce peak memory usage. 
Applies pruning in Decision Trees or Neural Networks to remove unnecessary neurons. 

- Complexity Awareness: 
Provide reasoning for time and space complexity of chosen methods. For example, discuss why certain implementation would decrease complexity. 

- Innovative Adjustments: 
Incorporate creative solutions like hashing or use PCA for dimensionality reduction where applicable. 

- Clear Documentation: 
Each optimization or choice is justified with respect to device constraints and expected performance gains. 
 
**Evaluate correctness and efficiency**
 
- Accuracy on MNIST subset.
Memory Usage measured in KB/MB should be measured and not exceed the requested one. 
Prototype for both algoritms recognises at least 75% of the testcases (applied from same database) 
Analyse runtime performance (time per image and training time). 

- Comparative Analysis: 
Present a clear comparison table or chart for the two algorithms (Decision Tree vs Neural Network) across all metrics (Accuracy (%), Memory (KB) ,Training time (seconds) ).

- Visualization: 
Create plots (e.g., accuracy vs memory trade-off, confusion matrix for classification) and interpret the results. Explain why one of the algorithms performs better or is better suited for the problem at hand. Explain how optimizations impact performance. 
- Validation: 
Confirm correctness through test cases (e.g., verifying sample digits). 
Professional Presentation: 
Results are well-structured, labelled, and easy to interpret. 