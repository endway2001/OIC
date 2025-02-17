Federated Learning System for Large-Scale IoT Networks
This repository implements a state-of-the-art Federated Learning (FL) system tailored for decentralized IoT networks. It combines advanced techniques such as Graph Neural Networks (GNN), Deep Reinforcement Learning (DRL), and semi-synchronous training to address challenges in scalability, resource efficiency, and model accuracy. Below is an overview of the system's workflow and key innovations.

System Workflow
Device Clustering with GNN-KMeans
Devices are grouped into logical clusters based on their data distribution, characteristics, and network constraints. A Graph Neural Network (GNN) models device relationships, and KMeans clustering assigns devices to clusters with similar traits. This ensures efficient resource allocation and reduces variance during model aggregation.

Hybrid Data Redistribution
Within each cluster, devices exchange portions of their datasets to balance label diversity and sample quantity. A threshold-based redistribution policy prioritizes devices with less diverse data while respecting privacy constraints, improving local model representativeness.

Device Assignment and Scheduling with DRL-PPO
Cluster-to-Edge Assignment : A DRL agent using Proximal Policy Optimization (PPO) assigns clusters to edge servers, optimizing bandwidth and server capacity utilization.
Device Scheduling : Another DRL-PPO agent selects the optimal subset of devices within each cluster for training, considering energy usage, bandwidth availability, and data diversity.
Semi-Synchronous Federated Learning
Edge-Level Training : Each edge server trains its assigned devices sequentially but independently of other edge servers. Device-specific characteristics (e.g., CPU power, memory) influence batch size, training time, and energy consumption.
Synchronous Aggregation : Models from devices within an edge server are aggregated synchronously, and edge-level models are sent to the cloud for global aggregation.
Dynamic Adaptation : Device assignments and schedules are recalculated after each global iteration to adapt to changing conditions.

Metrics Logging and Analysis
Comprehensive metrics such as energy consumption, time delays, and bandwidth usage are tracked across devices, edge servers, and the cloud. These metrics are saved as JSON files for analysis and debugging.

Key Innovations
Device-Specific Training : Local training accounts for device-specific CPU power and memory capacity, optimizing batch sizes, training times, and energy consumption.
Concurrency Control : Limits the number of concurrently active edge servers to respect resource constraints.
Dynamic Adaptation : Recalculates device assignments and schedules after each global iteration, ensuring sustained performance in dynamic environments.

Benefits of the System
Efficiency : Optimized use of computational resources at devices and edge servers, reducing communication costs and delays.
Scalability : Supports large-scale IoT networks with diverse devices and dynamic conditions.
Accuracy : Balanced data distribution and optimal scheduling enhance global model performance.
Adaptability : Dynamic adjustments ensure sustained performance in changing environments.
