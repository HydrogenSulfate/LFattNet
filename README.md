# LFattNet: Attention-based View Selection Networks for Light-field Disparity Estimation

<img src="/images/paper_concept.jpg" width="555" align=center />

**Attention-based View Selection Networks for Light-field Disparity Estimation** 

Yu-Ju Tsai,<sup>1</sup> Yu-Lun Liu,<sup>1,2</sup> Ming Ouhyoung,<sup>1</sup> Yung-Yu Chuang<sup>1</sup>  
<sup>1</sup>National Taiwan University, <sup>2</sup>MediaTek  

AAAI Conference on Artificial Intelligence (AAAI), Feb 2020  

- [(Paper Link)](/paper/aaai2020_LFattNet_camera_ready.pdf)
- Contact: <r06922009@cmlab.csie.ntu.edu.tw>, <yulunliu@cmlab.csie.ntu.edu.tw>  

## Network Architecture
![Network Architecture](/images/network.jpg)

# SOTA on 4D Light Field Benchmark
- We achieve **TOP rank performance** for most of the error matrices on the benchmark.

<img src="/images/benchmark.PNG" width="555" align=center />  

- For more detail comparison, please use the link below.
- [Benchmark link](https://lightfield-analysis.uni-konstanz.de/benchmark/table?column-type=images&metric=badpix_0070)

# Environment
```
Ubuntu            16.04
Python            3.5.2
Tensorflow-gpu    1.10
CUDA              9.0.176
Cudnn             7.1.4
```

# Train LFattNet
- Download HCI Light field dataset from <http://hci-lightfield.iwr.uni-heidelberg.de/>.  
- Unzip the LF dataset and move **'additional/, training/, test/, stratified/ '** into the **'hci_dataset/'**.
- Check the code in **'LFattNet_func/func_model_81.py'** and use the code at line 247.
- Run `python LFattNet_train.py`
  - Checkpoint files will be saved in **'LFattNet_checkpoints/LFattNet_ckp/iterXXXX_valmseXXXX_bpXXX.hdf5'**.
  - Training process will be saved in 
    - **'LFattNet_output/LFattNet/train_iterXXXXX.jpg'**
    - **'LFattNet_output/LFattNet/val_iterXXXXX.jpg'**.

# Evaluate LFattNet
- Check the code in **'LFattNet_func/func_model_81.py'** and use the code at line 250.
- Run `python LFattNet_evaluation.py`
  - To use your own model, you can modify the import model at line 78 like below:
    - `path_weight='./pretrain_model_9x9.hdf5'`

# Citation
```
@inproceedings{Tsai:2020:ABV,
        author = {Tsai, Yu-Ju and Liu, Yu-Lun and Ouhyoung, Ming and Chuang, Yung-Yu},
        title = {Attention-based View Selection Networks for Light-field Disparity Estimation},
        booktitle = {Proceedings of the 34th Conference on Artificial Intelligence (AAAI)},
        year = {2020}
}
```

Last modified data: 2020/09/14.

The code is modified and heavily borrowed from EPINET: <https://github.com/chshin10/epinet>
