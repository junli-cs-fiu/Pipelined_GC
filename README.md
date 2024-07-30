# Pipelined_GC
With the increasing demand for large-scale training, distributed machine learning, such as distributed stochastic gradient descent (SGD),  has been more common. Meanwhile, stragglers are inevitable in distributed infrastructures. Therefore, mitigating the effect of stragglers is essential research.

Since partial gradients can still make a model converge, ignore-straggler SGD (IS-SGD),  was proposed to tolerate stragglers straightforwardly. However, such methods can only leverage partial gradients of all data samples. Afterward, gradient coding (GC) was proposed to recover the full gradients with the results from a subset of all workers. However, each worker needs to compute the gradients of more data samples (redundancy) than usual.

Combining the advantages of IS-SGD and GC, in this project, we propose a pipeline-based training algorithm. Removing the redundancy for workers,  the proposed algorithm can keep the same ability to tolerate stragglers as GC by leveraging the stale gradients.
