
# 高级计算机体系结构大作业
sysu2023
数据集：https://github.com/TimingPredict/Dataset
原仓库README如下
### TimingPredict
This is the official open source repository for "A Timing Engine Inspired Graph Neural Network Model for Pre-Routing Slack Prediction" (DAC 2022).

#### Dataset
Please refer to [our Dataset repo](https://github.com/TimingPredict/Dataset) for download instructions and documentation.

#### Usage
First, download the dataset and extract to `<repo root>/data/`.

Then, download our pre-trained weight [here](https://disk.pku.edu.cn:443/link/2955DDB88C64B783A9A0B93BCCE21B87) or [here](https://cloud.guozz.cn/s/nRtq) or [here](https://drive.google.com/file/d/1lrr4qFlpkdjQRZjIEb5bGEHfC5FJWG61/view?usp=sharing) and put it under `<repo root>/checkpoints/08_atcd_specul/15799.pth`. (Note that Google drive is showing it as an archive but please download it as a whole.)

Finally, run the following command:

``` shell
python train_gnn.py --test_iter 15799 --checkpoint 08_atcd_specul
```

This prints two tables indicating the net delay and arrival time prediction results, same as that in our paper.

##### Code structure
`data_graph.py`: the data reader and pre-processor.

`model.py`: our customized GNN model implementation (please refer to the class `NetConv`, `SignalProp`, and `TimingGCN`). also inside it is our GCNII baseline implementation.

`train_gnn.py`: the model training and testing logic.

`train_stat_rf.py`, `train_deepgnn.py`: model training and testing for random forest and deep GCNII baselines.

#### Reference
Please cite our work if you find our code useful.

``` tex
@inproceedings{mltimerdac22,
 author = {Guo, Zizheng and Liu, Mingjie and Gu, Jiaqi and Zhang, Shuhan and Pan, David Z. and Lin, Yibo},
 booktitle = {Proceedings of the 59th Annual Design Automation Conference 2022},
 organization = {ACM},
 title = {A Timing Engine Inspired Graph Neural Network Model for Pre-Routing Slack Prediction},
 year = {2022}
}
```




