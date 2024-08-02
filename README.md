# Pipelined_GC
###  Abstract

With the increasing demand for large-scale training, distributed machine learning, such as distributed stochastic gradient descent (SGD), has been more common. Meanwhile, stragglers are inevitable in distributed infrastructures. Therefore, mitigating the effect of stragglers is essential research in distributed machine learning.

Since partial gradients can still make a model converge, ignore-straggler SGD (IS-SGD) was proposed to tolerate stragglers straightforwardly. However, such methods can only leverage partial gradients of all data samples. Afterward, gradient coding (GC) was proposed to recover the full gradients with the results from a subset of all workers. However, each worker needs to compute the gradients of more data samples (redundancy) than usual.

In this project, we propose pipelined gradient coding (PGC) that achieves the benefits of IS-SGD and GC, eliminating redundancy while maintaining straggler tolerance by leveraging stale gradients. This project not only addresses critical challenges in cloud computing but also contributes valuable insights into efficient distributed training methodologies. 



### Budget and Justification

To implement and demonstrate PGC using a real distributed environment, we expect to set up a cluster with $25$ nodes on Google Cloud Cluster (GCP), including $24$ worker nodes and one master node to train common models and datasets in a distributed manner. Specifically, we plan to use $25$ $\times$ N2-HighMem-2 instances for one month. A cost estimation from the GCP is presented as follows:

| **Item**               | **Description**                                          | **Estimated Cost (USD)** |
| ---------------------- | -------------------------------------------------------- | ------------------------ |
| Regular compute engine | $25$ $\times$ N2-HighMem-2 $24$ hours/day for $1$ months | \$2476.01             |

Table 1: Cost Estimation Table



To demonstrate the effectiveness of PGC, we plan to train at least three different combinations of datasets and models. To ensure the reproducibility of our algorithm, we will use different random seeds for multiple training runs and present the average performance. To efficiently utilize the cloud resources, we will first select suitable models and datasets and complete parameter tuning on our local server. To showcase the performance of PGC, we will compare it against three state-of-the-art coding algorithms. Therefore, we need to implement four different coding algorithms for each specific model and dataset combination.

We will carefully select combinations of datasets and models to ensure the experiment duration remains within budget.  If there is remaining time, it will be used for additional experiments, such as those needed for algorithm optimization and adjustments.



### Timeline

We have already completed foundational work and need two more months to finalize the theoretical work and optimize the algorithm. The specific workload will be conducted in two phases:

*   Phase $1$ ($1$ month): 
    *   Finalize the theoretical work, such as optimizing the algorithm.
    *   Design the specific plan of experiments, such as the selection of datasets and parameters.
    *   Simulate the distributed training using a local server for validation.
*   Phase $2$ ($1$ month): 
    *   Set up the cloud environment.
    *   Conduct the designed experiments and collect data.

