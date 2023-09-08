![Python >=3.6](https://img.shields.io/badge/Python->=3.6-yellow.svg)
![PyTorch >=1.10](https://img.shields.io/badge/PyTorch->=1.10-blue.svg)

# Spectral Aware Softmax for Visible-Infrared Person Re-Identification
The official repository for Spectral Aware Softmax for Visible-Infrared Person Re-Identification [[pdf]](https://arxiv.org/pdf/2302.01512.pdf)

### Prepare Datasets

- (1) RegDB Dataset [3]: The RegDB dataset can be downloaded from this [website](http://dm.dongguk.edu/link.html) by submitting a copyright form.

    - (Named: "Dongguk Body-based Person Recognition Database (DBPerson-Recog-DB1)" on their website). 
  
- (2) SYSU-MM01 Dataset [4]: The SYSU-MM01 dataset can be downloaded from this [website](http://isee.sysu.edu.cn/project/RGBIRReID.htm).

   - run `python pre_process_sysu.py` to pepare the dataset, the training data will be stored in ".npy" format.

## Training

We utilize 1 3090 GPU for training and you can train the SA-Softmax with:

```bash
python train_sas.py --gpu 'your device id' --dataset 'sysu or regdb'
```

**Some examples:**
```bash
# SYSU-MM01
python train_sas.py --gpu 0 --dataset sysu
```

## Evaluation
```bash
python test.py --mode 'mode for SYSU-MM01' --resume 'model_path' --gpu 'your device id' --dataset 'sysu or regdb'
```

**Some examples:**
```bash
# SYSU-MM01
python test.py --mode all --resume SAS_sysu.t --gpu 0 --dataset sysu
```


## Citation
Please kindly cite this paper in your publications if it helps your research:
```bash
@article{tan2023exploring,
  title={Exploring invariant representation for visible-infrared person re-identification},
  author={Tan, Lei and Zhang, Yukang and Shen, Shengmei and Wang, Yan and Dai, Pingyang and Lin, Xianming and Wu, Yongjian and Ji, Rongrong},
  journal={arXiv preprint arXiv:2302.00884},
  year={2023}
}
```

## Acknowledgement
Our code is based on [Cross-Modal-Re-ID-baseline](https://github.com/mangye16/Cross-Modal-Re-ID-baseline)[1, 2]

## References
[1] M. Ye, J. Shen, G. Lin, T. Xiang, L. Shao, and S. C., Hoi. Deep learning for person re-identification: A survey and outlook. IEEE Transactions on Pattern Analysis and Machine Intelligence (TPAMI), 2020.

[2] M. Ye, X. Lan, Z. Wang, and P. C. Yuen. Bi-directional Center-Constrained Top-Ranking for Visible Thermal Person Re-Identification. IEEE Transactions on Information Forensics and Security (TIFS), 2019.

## Contact

If you have any question, please feel free to contact us. E-mail: [tanlei@stu.xmu.edu.cn](mailto:tanlei@stu.xmu.edu.cn)
