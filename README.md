# EvoGraph: Evolutionary Dynamics in Adaptive Hypergraphs

EvoGraph is a computational model and simulation exploring evolutionary adaptation within a hypergraph system. 
Nodes represent evolving entities governed by distinct mutation rates, energy constraints, and interaction dynamics.
EvoGraph try to model biological evolution and neural network principles to observe how complex systems adapt under energy limitations and feedback-based mutations.

---

## Overview
EvoGraph simulates adaptive evolutionary dynamics in a hypergraph structure, where nodes mutate and interact with neighbors through hyperedges. 
These interactions are modulated by energy availability, mutation rate oscillation, and feedback loops that adjust node fitness and adaptability. EvoGraph is particularly suited to study complex adaptive systems, including neural networks and genetic evolution in artificial systems.

## Core Features
- **Adaptive DNA Encoding*: Nodes have DNA encoding parameters such as mutation rate, interaction strength, and energy thresholds, tailored to species types.
- **Oscillatory Mutation Rates*: Mutation rates oscillate based on feedback and constraints, enabling controlled adaptation.
- **Dynamic Hyperedges*: Nodes form cooperative or competitive hyperedges, which adjust based on mutation rates and energy interactions.
- **Energy and Feedback Dynamics*: Energy availability and feedback directly influence mutation rates, fitness, and long-term adaptation.

## System Requirements
EvoGraph requires Python 3.x.

## Project Configuration
The `config` dictionary provides tunable parameters:
- `global_mutation_rate`: Sets a base mutation rate for the entire system.
- `interaction_strength_range`: Defines min/max interaction strength values for node interactions.
- `mutation_rate_range`: Sets mutation rate bounds for nodes.
- `energy_threshold`: Minimum energy required to engage in node interactions.
- `environment_energy`: Environmental energy for node regeneration.
- `oscillatory_mutation`: Enables/disables mutation rate oscillations.
- `log_file`: File name for logging evolution data.

These parameters allow EvoGraph to model different evolutionary and energy scenarios, affecting species adaptation and hyperedge formation.

## Theory and Mechanisms

### DNA and Mutation Mechanisms
Each node is assigned a DNA class (`NodeDNA`), which encodes:
- **Interaction Strength*: Governs interaction power between nodes.
- **Mutation Rate*: Determines the probability and scale of mutations per node.
- **State*: Binary state value, enabling Cellular Automata-like (CA) behavior.
- **Activation Threshold*: Represents a threshold for energy-based activation, inspired by neural activation functions.
- **Energy*: Initial energy for interactions and mutation, which is dynamically replenished or consumed.

## Species-Specific DNA: 
- **Species A* has a higher mutation rate but incurs a greater energy cost.
- **Species B* has a lower mutation rate, optimized for energy efficiency.

### Hypergraph and Interaction Dynamics
EvoGraph uses a hypergraph where nodes (entities) form both **cooperative* and **competitive hyperedges*. 
Hyperedges are reformed dynamically based on changes in node mutation rates and energy levels, representing an evolving network.

*Interaction Dynamics*:
1. Nodes interact based on energy thresholds and their own interaction strength.
2. Weighted interactions occur within hyperedges, adjusting each node’s activation level based on the weighted average of neighboring nodes.
3. *Activation Function**: Uses a sigmoid function to determine the activation level, providing neural-inspired behavior.

### Energy Sources and Feedback Mechanisms
Each node is linked to external energy sources that replenish energy periodically. Nodes undergo a feedback loop:
- *Positive Feedback**: Increases mutation rate and fitness, with energy gains.
- *Negative Feedback**: Decreases mutation rate, reducing energy and fitness.

Feedback influences future interactions and mutation behavior, enabling nodes to adapt according to environmental conditions and resource availability.

## Running the Simulation
To begin the simulation:
1. Clone the repository:
    ```
    git clone https://github.com/LievSS/EvoGraph.git
    cd EvoGraph
    ```

2. Run the simulation:
    ```
    python main.py
    ```

This will initialize a hypergraph with nodes of both species, each linked to energy sources, and will evolve the system over generations. Each generation logs metrics to `evolution_data.csv`, including:
- Node ID, Species, Mutation Rate, Interaction Strength, Fitness, Energy, Activation Level.

### Sample Output
Data logs include:
```csv
Generation, Node_ID, Species_Type, Mutation_Rate, Interaction_Strength, Fitness, Energy, Activation_Level
0, 1, A, 0.25, 1.2, 1, 80, 0.5
...
```

## Contributing
Contributions are welcome! Feel free to open issues for feature requests or bug reports. If contributing code, please fork the repository and submit a pull request.
