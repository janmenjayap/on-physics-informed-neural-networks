## Utilizing Physics-Informed Neural Networks (PINNs) and Lagaris' Approach for Solving Partial Differential Equations

This repository encompasses Python code and Jupyter notebooks exemplifying the application of Physics-Informed Neural Networks (PINNs) and Lagaris' approach to address Partial Differential Equations (PDEs).

### Introduction

The computational expense associated with traditional numerical methods for solving PDEs, particularly for high-dimensional problems, prompts exploration into alternative methodologies. PINNs represent an innovative approach harnessing neural network capabilities to solve PDEs with constrained data. These networks embed the physical principles within the learning process, leveraging the governing equations as part of the loss function. This project showcases the efficacy of PINNs in addressing diverse PDEs. Furthermore, the Lagaris Approach, a simpler method utilizing Artificial Neural Networks (ANNs) for PDE solutions, has been explored for comparison. The Lagaris Approach focuses on direct data fitting without explicitly incorporating the governing PDE constraints during training.

These methodologies draw inspiration from [1] and [2], exemplifying distinct approaches to solving PDEs: one driven by embedding physics into neural network learning ([2]), and the other relying more on direct data-driven fitting ([1]).

### Examples

This repository includes illustrative examples that exhibit the distinct approaches:

- **1D-Advection.ipynb:** Demonstrates the solution to the 1D advection equation employing a PINN, where the network learns to adhere to the governing PDE while approximating the solution.
  ![image](https://user-images.githubusercontent.com/78913240/234979875-6b799c67-7985-46d6-a233-c00bb3556dbf.png)
  - *Description*: This notebook focuses on solving the 1D advection equation (\( u_t + au_x = 0 \)) using a PINN.

- **PDE_using_Lagaris_Approch.ipynb:** Showcases the resolution of a specific PDE outlined in [1], utilizing the Lagaris Approach, which focuses on direct data fitting without explicit integration of the PDE constraints in the training process.
  ![image](https://user-images.githubusercontent.com/78913240/234981409-70d400d5-345b-4450-bc30-9241a5ec9dfd.png)
  - *Description*: This notebook demonstrates solving a particular PDE using Lagaris' approach with a single dense layer and 10 neurons.

- **PDE_using_PINNs.ipynb :** Addresses the same PDE as previously mentioned, employing the PINNs (Raissi Approach) detailed in [2], where the network learns to satisfy the PDE constraints as part of the training.
  ![image](https://user-images.githubusercontent.com/78913240/234987466-29867eb4-df2c-46c2-bbe6-e151233a4a83.png)
  - *Description*: This notebook demonstrates solving the same PDE using PINNs, focusing on the Raissi Approach from [2].

### Results

#### PDE solution using PINNs
![image](https://user-images.githubusercontent.com/78913240/234987466-29867eb4-df2c-46c2-bbe6-e151233a4a83.png)

#### PDE solution using Lagaris Approach
![image](https://user-images.githubusercontent.com/78913240/234987482-0e751293-16da-47ee-8f9c-a44d09fc13a7.png)

#### 1D-Advection using PINNs
![image](https://user-images.githubusercontent.com/78913240/234990371-8b4eedcc-b709-42e0-a619-5d81671afffa.png)
![image](https://user-images.githubusercontent.com/78913240/234990036-d70047d8-d88a-4228-b9eb-fd85fc37bb89.png)

### Discussion

The PINNs method proves effective for handling high-dimensional problems with limited data by integrating the physics within the learning process, whereas the Lagaris Approach, simpler in design, emphasizes direct data fitting. PINNs offer versatility and robustness, especially when dealing with limited data, while Lagaris' approach showcases simplicity but might lack the robustness needed for complex problems.

These distinct methodologies offer varying trade-offs in complexity, data dependency, and computational resources, making the choice between them contingent upon the specific problem, available data, computational resources, and the desired level of accuracy.

### Physics-Informed Neural Networks (PINNs)

#### Overview
PINNs are a class of neural networks designed to solve forward and inverse problems associated with PDEs. They combine the power of neural networks with the physical principles embedded in the governing equations.

#### Methodology
1. **Loss Function Incorporating Physics:** PINNs leverage the PDEs themselves as part of the loss function, ensuring that the network learns to satisfy the underlying physics.
2. **Limited Data Usage:** Unlike traditional numerical methods, PINNs can work with limited data and don't rely on discretizing the entire domain.
3. **Training Strategy:** These networks are trained using both supervised learning (data fitting) and unsupervised learning (enforcing the PDE constraints).

#### Advantages
- Efficient with limited data.
- Can handle high-dimensional problems.
- Offers a data-driven approach to solving PDEs.

#### Example
In the provided example, the PINNs are used to solve PDEs by training a neural network to approximate the solutions while adhering to the governing equations.

### Lagaris Approach

#### Overview
The Lagaris Approach is a specific methodology developed for solving PDEs using Artificial Neural Networks (ANNs).

#### Methodology
1. **Network Architecture:** Utilizes neural networks, typically with a straightforward architecture, such as a single dense layer with a limited number of neurons.
2. **Direct Data Fitting:** Focuses on fitting the provided data points directly without explicitly enforcing the governing PDE constraints.
3. **Data-driven Resolution:** Aims to approximate the solution purely based on available data without explicitly embedding the physics into the loss function.

#### Advantages
- Simplicity in approach and implementation.
- Can offer decent approximations for certain types of problems with limited computational complexity.

#### Example
In the given instance, the Lagaris Approach is applied to solve a specific PDE by directly fitting the data points without incorporating the PDE constraints explicitly in the training process.

### Comparison

- **Philosophy:** PINNs focus on embedding the physics within the learning process, whereas Lagaris Approach relies more on data-driven fitting without explicit incorporation of the physics.
- **Complexity:** PINNs tend to be more flexible and robust for various PDEs, especially those with limited data. Lagaris' approach, being more simplistic, might work well for specific cases but might lack robustness for complex problems.
- **Data Dependency:** PINNs are more versatile with limited data, whereas Lagaris' approach heavily relies on the data provided for accurate approximation.

These methods cater to different paradigms in solving PDEs, each with its strengths and areas of application. Choosing between them often depends on the specific problem, available data, computational resources, and the desired level of accuracy.

### References

[1] Lagaris, I. E., Likas, A., & Fotiadis, D. I. (1997). Artificial neural networks for solving ordinary and partial differential equations. *IEEE Transactions on Neural Networks*, 9(5), 987-1000. [Link](https://arxiv.org/pdf/physics/9705023.pdf)

[2] Raissi, M., Perdikaris, P., & Karniadakis, G. E. (2017). Physics-informed neural networks: A deep learning framework for solving forward and inverse problems involving nonlinear partial differential equations. *Journal of Computational Physics*, 378, 686-707. [PINNs Paper](https://arxiv.org/pdf/1711.10561.pdf)
