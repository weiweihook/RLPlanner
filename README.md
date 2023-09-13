# 2.5D_system_detail

## Configurations
We use .cfg file to describe a 2.5D system. Here we briefly describe the options in the .cfg file.
### [chiplets]
- **chiplet_count**: the number of chiplets in the 2.5D system.
- **widths**: the width of each chiplet, separated by ",".
- **heights**: the height of each chiplet, separated by ",".
- **powers**: the power of each chiplet, separated by ",".
- **connections**: the connection matrix of chiplets. The i-th row and j-th column in the matrix is the bandwidth from chiplet i to chiplet j.

We place eight examples under configs/ directory, which we used in our paper. It contains two kinds of 2.5D system. 

### 1. Open source systems
- Multi-GPU system[1]
- CPU-DRAM system[2]
- Huawei Ascend 910 system [3]

### 2. Conceptual systems
- Case1, Case4: have the same six chiplet, the same width and height, but have different power values
- Case2: consists of three HBMs and three CPUs
- Case3, Case5: contain six chiplet with different sizes

In the future, we will randomly generate more 2.5D systems with different sizes and quantities for experimental verification.

## Experiment
### Setting
| Hyperparameter | Value |
| :-------------------------:|:-------------------------: |
| Activation Function | Linear rectification function|
| Optimizer           | Adam |
| Learning Rate       | 2.5E-4 |
| Clip Gradient Norm  | 0.5 |
| Total Epoch         | 600 |
| Batch Size          | 480 |
| Minibatch Size      | 4   |
| Clipping Coefficient| 0.1 |
| Entropy Coefficient | 0.01|
| Value Coefficient   | 0.5 |
| Discount(γ)         | 0.99|
      

### Results
### Comparisons of reward, wirelength, temperature and runtime
![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/comparison_RWTR.png)

### Comparisons of the final placement
- case1
|  |  |
| :-------------------------:|:-------------------------: |
|  |  |
|  |  |

- case2
|  |  |
| :-------------------------:|:-------------------------: |
|  |  |
|  |  |

- case3
|  |  |
| :-------------------------:|:-------------------------: |
|  |  |
|  |  |

- case4
|  |  |
| :-------------------------:|:-------------------------: |
|  |  |
|  |  |

- case5
|  |  |
| :-------------------------:|:-------------------------: |
|  |  |
|  |  |

- Multi-GPU
|  |  |
| :-------------------------:|:-------------------------: |
|  |  |
|  |  |

- Micro150
|  |  |
| :-------------------------:|:-------------------------: |
|  |  |
|  |  |

- Ascend910
|  |  |
| :-------------------------:|:-------------------------: |
|  |  |
|  |  |

## References
[1]Y. Ma, L. Delshadtehrani, C. Demirkiran, J. L. Abellan, and A. Joshi, “Tap-2.5 d: A thermally-aware chiplet placement methodology for 2.5 d systems,” in 2021 Design, Automation & Test in Europe Conference & Exhibition (DATE). IEEE, 2021, pp. 1246–1251.

[2]A. Kannan, N. E. Jerger, and G. H. Loh, “Enabling interposer-based disintegration of multi-core processors,” in Proceedings of the 48th international symposium on Microarchitecture, 2015, pp. 546–558.

[3]Huawei ascend 910 provides an nVidia AI training alternative. [Online]. Available: https://www.servethehome.com/huawei-ascend-910-providesa-nvidia-aitraining- alternative/
