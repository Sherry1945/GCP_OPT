# Towards A Deeper Understanding of Global Covariance Pooling in Deep Learning: An Optimization Perspective
Qilong Wang,  Zhaolin Zhang*, Mingze Gao*, Jiangtao Xie, Pengfei Zhu†, Peihua Li, Wangmeng Zuo, and Qinghua Hu† 
## Abstract
Global covariance pooling (GCP) as an effective alternative to global average pooling has shown good capacity to improve deep convolutional neural networks (CNNs) in a variety of vision tasks. Although promising performance, it is still an open problem on how GCP (especially its post-normalization) works in deep learning. In this paper, we make the effort towards understanding the effect of GCP on deep learning from an optimization perspective. Specifically, we first analyze behavior of GCP with matrix power normalization on optimization loss and gradient computation of deep architectures. Our findings show that GCP can improve Lipschitzness of optimization loss and achieve flatter local minima, while improving gradient predictiveness and functioning as a special pre-conditioner on gradients. Then, we explore the effect of post-normalization on GCP from the model optimization perspective, which encourages us to propose a simple yet effective normalization, namely DropCov. Based on above findings, we point out several merits of deep GCP that have not been recognized previously or fully explored, including faster convergence, stronger model robustness and better generalization across tasks. Extensive experimental results using both CNNs and vision transformers on diversified vision tasks provide strong support to our findings while verifying the effectiveness of our method.
## References

 [DropCov: A Simple yet Effective Method for Improving Deep Architectures](https://papers.nips.cc/paper_files/paper/2022/hash/d9888cc7baa04c2e44e8115588133515-Abstract-Conference.html)  Qilong Wang, Mingze Gao, Zhaolin Zhang, Jiangtao Xie, Peihua Li, Qinghua Hu.Advances in Neural Information Processing Systems (NeurIPS), 2022.
 
 [What Deep CNNs Benefit from Global Covariance Pooling: An Optimization
Perspective](https://openaccess.thecvf.com/content_CVPR_2020/papers/Wang_What_Deep_CNNs_Benefit_From_Global_Covariance_Pooling_An_Optimization_CVPR_2020_paper.pdf)  Qilong Wang, Li Zhang, Banggu Wu, Dongwei Ren, Peihua Li, Wangmeng Zuo, Qinghua Hu. IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR),2020.


## Implementation 
|Works         | Paper | Mindspore Code| Pytorch Code|                                                         
| ------------------ | ----- | ------- | ------- | 
| What Deep CNNs Benefit from Global Covariance Pooling: An Optimization Perspective  |  [Link](https://openaccess.thecvf.com/content_CVPR_2020/papers/Wang_What_Deep_CNNs_Benefit_From_Global_Covariance_Pooling_An_Optimization_CVPR_2020_paper.pdf)|[Link](https://github.com/Terror03/GCP-OPT)   | [Link](https://github.com/ZhangLi-CS/GCP_Optimization) |
| DropCov: A Simple yet Effective Method for Improving Deep Architectures   | [Link](https://papers.nips.cc/paper_files/paper/2022/hash/d9888cc7baa04c2e44e8115588133515-Abstract-Conference.html)  |   [Link](https://github.com/Sherry1945/Dropcov_mindspore)   | [Link](https://github.com/mingzeG/DropCov) |

## Results
Results with Mindspore
|Method(Mindspore)           | Acc@1(%) | #Params.(M) | FLOPs(G) | Checkpoint                                                          |
| ------------------ | ----- | ------- | ----- | ------------------------------------------------------------ |
| ResNet-18   |  70.53 |  11.7   |   1.81  |               |
| ResNet-18+Fast-MPN(Ours)   | 74.64  |   19.6  |  3.11   |[Download](https://drive.google.com/file/d/1kpBpbYpWQfSzSav7v8Ms7dn1SaUlOlMk/view?usp=drive_link)|
| ResNet-18+Drop-COV(Ours)   | 73.8  |   19.3  |  3.11   |[Download](https://drive.google.com/file/d/1zVDDmmQWQ-CDDoxjaolkcjI3MACE-rxx/view?usp=drive_link)|
| ResNet-34   |  73.68 |  21.8   |   3.66  |               |
| ResNet-34+Fast-MPN(Ours)   |  76.27 |   29.7  |  5.56   |[Download](https://drive.google.com/file/d/1T0YCzz-A-V2GI1tjihCHIjug93nFSQ91/view?usp=drive_link)|
| ResNet-34+Drop-COV(Ours)   | 76.13  |   29.6  |  5.56   |[Download](https://drive.google.com/file/d/1-gvogrLlRSnpzigvevLPV1GKAHF0vr2K/view?usp=drive_link)|
| ResNet-50   |  76.07 |  25.6   |   3.86  |               |
| ResNet-50+Fast-MPN(Ours)   | 77.71  |   32.3  |  6.19   |[Download](https://drive.google.com/file/d/1aF-By_pMhbCu82Gl73sFyz4qlNS25ayJ/view?usp=drive_link)|
| ResNet-50+Drop-COV(Ours)   | 77.77  |   32.0  |  6.19   |[Download](https://drive.google.com/file/d/1PBy8evHi-xiJHiTWgqrUs8jTH58hJM2n/view?usp=share_link)|

Results with Pytorch
|Method(Pytorch)           | Acc@1(%) | #Params.(M) | FLOPs(G) | Checkpoint|                                        
| ------------------ | ----- | ------- | ----- | ------------------------------------------------------------ |
| ResNet-34   |  74.19 |  21.8   |   3.66  |               |
| ResNet-34+Fast-MPN(Ours)   |  76.80 |   29.7  |  5.56   |[Download](https://drive.google.com/file/d/1T0YCzz-A-V2GI1tjihCHIjug93nFSQ91/view?usp=drive_link)|
| ResNet-34+Drop-COV(Ours)   | 76.81  |   29.6  |  5.56   |[Download](https://drive.google.com/open?id=1C3m6uicOuYoWiqRrt8ZUjgloa6iSLw-Y)|
| ResNet-50   |  76.02 |  25.6   |   3.86  |               |
| ResNet-50+Fast-MPN(Ours)   | 78.56  |   32.3  |  6.19   |[Download](https://drive.google.com/file/d/1aF-By_pMhbCu82Gl73sFyz4qlNS25ayJ/view?usp=drive_link)|
| ResNet-50+Drop-COV(Ours)   | 78.19  |   32.0  |  6.19   |[Download](https://drive.google.com/open?id=1TmnusKSArjKTTb28cnw2OzrUVc_DAi98)|
| ResNet-101   |  77.67 |  44.6  |  7.57 |               |
| ResNet-101+Fast-MPN(Ours)   | 79.47  |   51.3  |  9.90   |[Download](https://drive.google.com/open?id=1y8oI2IodJuG7R_gIdrYoXSTPafmszwMh)|
| ResNet-101+Drop-COV(Ours)   | 79.51 |   51.0 |9.90    |[Download](https://drive.google.com/file/d/1KJyAUXu11GFz6uLS1kGyZc1JM-pi-E37/view?usp=sharing)|
