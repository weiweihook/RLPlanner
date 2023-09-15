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
![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/comparison_all.png)

### Comparisons of the final placement
- case1

| RLPlanner | RLPlanner(dense reward)  |RLPlanner(dense reward)|
| :-------------------------:|:-------------------------: |:-------------------------: |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/cnn/case1.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/dense/case1.png)  | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/rnd/case1.png)|
| TAP-2.5D(Hotspot) | TAP-2.5D*(Table Model) | |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap1/case1.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap2/case1.png) | |

- case2

| RLPlanner | RLPlanner(dense reward)  |RLPlanner(dense reward)|
| :-------------------------:|:-------------------------: |:-------------------------: |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/cnn/case2.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/dense/case2.png)  | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/rnd/case2.png)|
| TAP-2.5D(Hotspot) | TAP-2.5D*(Table Model) | |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap1/case2.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap2/case2.png) | |

- case3

| RLPlanner | RLPlanner(dense reward)  |RLPlanner(dense reward)|
| :-------------------------:|:-------------------------: |:-------------------------: |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/cnn/case3.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/dense/case3.png)  | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/rnd/case3.png)|
| TAP-2.5D(Hotspot) | TAP-2.5D*(Table Model) | |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap1/case3.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap2/case3.png) | |

- case4

| RLPlanner | RLPlanner(dense reward)  |RLPlanner(dense reward)|
| :-------------------------:|:-------------------------: |:-------------------------: |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/cnn/case4.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/dense/case4.png)  | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/rnd/case4.png)|
| TAP-2.5D(Hotspot) | TAP-2.5D*(Table Model) | |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap1/case4.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap2/case4.png) | |

- case5

| RLPlanner | RLPlanner(dense reward)  |RLPlanner(dense reward)|
| :-------------------------:|:-------------------------: |:-------------------------: |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/cnn/case5.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/dense/case5.png)  | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/rnd/case5.png)|
| TAP-2.5D(Hotspot) | TAP-2.5D*(Table Model) | |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap1/case5.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap2/case5.png) | |

- Multi-GPU

| RLPlanner | RLPlanner(dense reward)  |RLPlanner(dense reward)|
| :-------------------------:|:-------------------------: |:-------------------------: |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/cnn/case7.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/dense/case7.png)  | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/rnd/case7.png)|
| TAP-2.5D(Hotspot) | TAP-2.5D*(Table Model) | |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap1/case71.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap2/case71.png) | |


- Micro150

| RLPlanner | RLPlanner(dense reward)  |RLPlanner(dense reward)|
| :-------------------------:|:-------------------------: |:-------------------------: |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/cnn/case8.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/dense/case8.png)  | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/rnd/case8.png)|
| TAP-2.5D(Hotspot) | TAP-2.5D*(Table Model) | |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap1/case8.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap2/case8.png) | |

- Ascend910

| RLPlanner | RLPlanner(dense reward)  |RLPlanner(dense reward)|
| :-------------------------:|:-------------------------: |:-------------------------: |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/cnn/case6.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/dense/case6.png)  | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/rnd/case6.png)|
| TAP-2.5D(Hotspot) | TAP-2.5D*(Table Model) | |
| ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap1/case6.png) | ![](https://github.com/weiweihook/2.5D-system-detail/blob/main/results/tap2/case6.png) | |

## References
[1]Y. Ma, L. Delshadtehrani, C. Demirkiran, J. L. Abellan, and A. Joshi, “Tap-2.5 d: A thermally-aware chiplet placement methodology for 2.5 d systems,” in 2021 Design, Automation & Test in Europe Conference & Exhibition (DATE). IEEE, 2021, pp. 1246–1251.

[2]A. Kannan, N. E. Jerger, and G. H. Loh, “Enabling interposer-based disintegration of multi-core processors,” in Proceedings of the 48th international symposium on Microarchitecture, 2015, pp. 546–558.

[3]Huawei ascend 910 provides an nVidia AI training alternative. [Online]. Available: https://www.servethehome.com/huawei-ascend-910-providesa-nvidia-aitraining- alternative/
