## Cross-Domain Model Fusion with mixture of Experts and Multi-Teacher Knowledge Distaillation

In this term project, we explored how to combine multiple lightweight ResNet image classifiers into a single model that can handle a larger set of classes while staying within strict limits on our model size and depth (8M parameters, 10 layers). We focused on 2 cases  
1. Task A: When the classifiers are trained on different classes
2. Task B: When the classifiers are trained on overlapping classes

To solve these problems, we proposed two main approaches. The first is a Mixture of Experts (MoE) model that uses a shared feature extractor, several expert networks, and a gating mechanism to decide which expert to use for each input. The second is a Knowledge Distillation (KD) approach, where we use several teacher models to guide a student model that learns to perform well across all classes.

Through experiments on subsets of CIFAR-100 and ImageNet, we showed that both methods can successfully merge the knowledge from different classifiers. The MoE model achieved 79.0% and 74.3% on Task A and B, respectively. The KD model achieved 81.3% and 80.0% on Task A and B, respectively. The KD model achieved the highest accuracy on both tasks, showing that it is a strong choice for unifying knowledge from multiple domains.

Overall, our methods offer practical solutions for building accurate and compact models in multi-domain settings. Future work could look into improving the gating strategy, trying other types of backbone networks, or applying these ideas to tasks beyond image classification.

The two implementations are available here: 
- https://github.com/Djanghao/cas771-moe
- https://github.com/Djanghao/cas771-knowledge-distillation.