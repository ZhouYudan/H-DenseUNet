# H-DenseUNet: Hybrid Densely Connected UNet for Liver and Tumor Segmentation from CT Volumes, TMI 2018. 
by [Xiaomeng Li](https://scholar.google.com/citations?user=uVTzPpoAAAAJ&hl=en), [Hao Chen](http://appsrv.cse.cuhk.edu.hk/~hchen/), [Xiaojuan Qi](https://xjqi.github.io/), [Qi Dou](http://appsrv.cse.cuhk.edu.hk/~qdou/), [Chi-Wing Fu](http://www.cse.cuhk.edu.hk/~cwfu/), [Pheng-Ann Heng](http://www.cse.cuhk.edu.hk/~pheng/). 

### Introduction

This repository is for our TMI 2018 paper '[H-DenseUNet: Hybrid Densely Connected UNet for Liver and Tumor Segmentation from CT Volumes](http://arxiv.org/pdf/1709.07330.pdf)'.

### Installation
This repository is based on Keras with Tensorflow backbone. Therefore, you need to install tensorflow. 

### Usage

1. Clone the repository:

   ```shell
   git clone https://github.com/yulequan/PU-Net.git
   cd PU-Net
   ```
2. Data preprocessing: 
   Download dataset from: [Liver Tumor Segmentation Challenge](https://drive.google.com/drive/folders/0B0vscETPGI1-Q1h1WFdEM2FHSUE)
   put 131 training data with segmentation masks under "data/TrainingData/" and 70 test data under "data/TestData/"
   Then data preprocessing, run:
   ```shell 
   python preprocessing.py 
   ```


3. Test our model:
   Download liver mask from [GoogleDrive](https://drive.google.com/file/d/14DFUoX877dWjaiau_5c5aI3j4JYxdEMm/view?usp=sharing) and put them in folder: 'livermask' 
   Download model from [GoogleDrive](https://drive.google.com/file/d/1sZgqnqjF_M3Bv_9M2kkfPZyPTrIoVttB/view?usp=sharing) and put them in folder: 'model'
   run:
   ```shell
   python test.py
   ```

4. Train 2D DenseUnet:
    First, you need to download the pretrained model from [GoogleDrive](https://drive.google.com/file/d/195LqUBwueXqhmRcznK20S7AK6NtGEHBM/view?usp=sharing), extract it and put it in folder 'model'.
    Then run:
   ```shell
   sh bash_train.sh
   ```

5, Train H-DenseUnet:

	First, Load your trained 2d model. 
	Then run: 
	```shell 
	sh bash_trainhybrid.sh
	```

### Evaluation code
We provide the code to calculate the metric NUC in the evaluation code folder. In order to use it, you need to install the CGAL library. Please refer [this link](https://www.cgal.org/download/linux.html) to install this library.
Then:
   ```shell
   cd evaluation_code
   cmake .
   make
   ./evaluation nicolo.off nicolo.xyz
```

## Citation

If H-DenseUNet is useful for your research, please consider citing:

	@article{li2018h,
	  title={H-DenseUNet: Hybrid Densely Connected UNet for Liver and Tumor Segmentation from CT Volumes},
	  author={Li, Xiaomeng and Chen, Hao and Qi, Xiaojuan and Dou, Qi and Fu, Chi-Wing and Heng, Pheng-Ann},
	  journal={IEEE Transactions on Medical Imaging},
	  year={2018},
	  publisher={IEEE}
	}

### Questions

Please contact 'xmli@cse.cuhk.edu.hk'

