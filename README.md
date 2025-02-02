# Learning Self-Supervised Behaviors with Graph Attention-based Architectures

This repository contains the anonymized code associated to the *Learning Self-Supervised Behaviors with Graph Attention-based Architectures* paper submitted at the CoLLAs 2022 Conference.

**Abstract**
Although humans live in an open-ended world and endlessly face new challenges, they do not have to learn from scratch each time they face the next one. Rather, they have access to a handful of previously learned skills, which they rapidly adapt to new situations. In artificial intelligence, autotelic agents—which are intrinsically motivated to represent and set their own goals—exhibit promising skill adaptation capabilities. However, these capabilities are highly constrained by their policy and goal space representations. In this paper, we propose to investigate the impact of these representations on the learning capabilities of autotelic agents. We study different implementations of autotelic agents using four types of Graph Neural Networks policy representations and two types of goal spaces, either geometric or predicate-based. We show that combining object-centered architectures that are expressive enough with semantic relational goals enables an efficient transfer between skills and promotes behavioral diversity. We also release our graph-based implementations to encourage further research in this direction.

![alt text](https://ibb.co/64S22ZN)

**Requirements**

* gym
* mujoco
* pytorch
* pandas
* matplotlib
* numpy

To reproduce the results, you need a machine with **24** cpus.


**Training Graph-based Autotelic Agents**

The following lines launch the training of our autotelic agents. When using semantic goal spaces, agents explore their behavioral space, discover new goals and attempt to learn them. When using continuous goal space, agents first select a class of goals based on the number of desired stacks. This selection is based on an LP-based Curriculum Learning which is shown to stabilize the learning procedure

```mpirun -np 24 python train.py --algo semantic```

```mpirun -np 2 --allow-run-as-root python train.py --algo semantic``` (for my own pc)

```mpirun -np 24 python train.py --algo continuous```

```mpirun -np 2 --allow-run-as-root python train.py --algo continuous``` (for my own pc)

Note: The folder configs/ contains the hyper-parameters used for both types of goal spaces. 

