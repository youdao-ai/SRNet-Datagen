# SRNet-Datagen - A data generator of SRNet

&nbsp;
## Introduction
This is a data generator of SRNet which is the model of paper *Editing Text in the wild*.

Our tensorflow reproducing of SRNet: [https://github.com/youdao-ai/SRNet](https://github.com/youdao-ai/SRNet)

Original paper: [*Editing Text in the wild*](https://arxiv.org/abs/1908.03047) by Liang Wu, Chengquan Zhang, Jiaming Liu, Junyu Han, Jingtuo Liu, Errui Ding and Xiang Bai.

This data generator project is simplified based on the following two projects.

[Synthtext](https://github.com/ankush-me/SynthText): Extracted the rendering part of the project and Adjusted to Python3 code to get `i_s`, `t_t`, `t_f` and `mask_t`

[Skeletonization-of-Digital-Patterns](https://github.com/anupamwadhwa/Skeletonization-of-Digital-Patterns): Adjusted this project to Python3 code to skeletonize mask_t and get `t_sk`.

&nbsp;
## Generate data
First prepare a directory of fonts and a background datasets without text, you can also prepare a word corpus for rendering.

You can adjust the data configurations in `Synthtext/data_cfg.py`. 

Then you adjust generating configurations in `cfg.py` including saving directory, the amount of data to generat and the number of processes to use.

Finally `Python datagen.py` and start generating.

You can also use this project to generate data online while training SRNet.

- `i_s`: styled text a rendering on background image

- `i_t`: standard text b rendering on gray background

- `t_sk`: skeletonization of styled text b.

- `t_t`: styled text b rendering on gray background

- `t_b`: background image

- `t_f`: styled text b rendering on background image

- `mask_t`: the binary mask of styled text b

![image](https://github.com/youdao-ai/SRNet/blob/master/examples/example/data.png)

From left to right, from top to bottom are examples of `i_s, i_t, t_sk, t_t, t_b, t_f, mask_t`

&nbsp;
## Requirements
- Python 3.6

- numpy

- opencv-python

&nbsp;
## Reference
- [Editing Text in the Wild](https://arxiv.org/abs/1908.03047)

- [Synthetic Data for Text Localisation in Natural Images](https://arxiv.org/abs/1604.06646)

- [A fast parallel algorithm for thinning digital patterns](http://www-prima.inrialpes.fr/perso/Tran/Draft/gateway.cfm.pdf)

