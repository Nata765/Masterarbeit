<<<<<<< HEAD
# Masterarbeit-code
## First try with VN-DGCNN

## Data Preparation
+ Part Segmentation: Download [ShapeNet] and save in `data/shapenetcore_partanno_segmentation_benchmark_v0_normal/`.
```
mkdir data
cd data

gdown https://drive.google.com/uc?id=1W3SEE-dY1sxvlECcOwWSDYemwHEUbJIS
tar -xvf shapenetcore_partanno_segmentation_benchmark_v0_normal.tar
rm shapenetcore_partanno_segmentation_benchmark_v0_normal.tar
```
## Usage

### Part Segmentation on ShapeNet

Training
```
python train_partseg.py --model vn_pointnet_partseg --rot ROTATION --log_dir LOG_DIR
```
```
python train_partseg.py --model vn_dgcnn_partseg --rot ROTATION --log_dir LOG_DIR
```
Evaluation
```
python test_partseg.py --model vn_pointnet_partseg --rot ROTATION --log_dir LOG_DIR
```
```
python test_partseg.py --model vn_dgcnn_partseg --rot ROTATION --log_dir LOG_DIR
```
For instance, to train a VN-DGCNN on aligned shapes and test it on SO(3)-rotated shapes, run
```
python train_partseg.py --model vn_dgcnn_partseg --rot aligned --log_dir vn_dgcnn/aligned/
```
```
python test_partseg.py --model vn_dgcnn_partseg --rot so3 --log_dir vn_dgcnn/aligned/
```

## Citation
Please cite this paper if you want to use it in your work,

    @article{deng2021vn,
      title={Vector Neurons: a general framework for SO(3)-equivariant networks},
      author={Deng, Congyue and Litany, Or and Duan, Yueqi and Poulenard, Adrien and Tagliasacchi, Andrea and Guibas, Leonidas},
      journal={arXiv preprint arXiv:2104.12229},
      year={2021}
    } 


