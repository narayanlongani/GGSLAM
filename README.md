<p align="center">

  <h1 align="center"> GGSLAM: An Object-Level SLAM System Using Gaussian Grouping and Splatting </h1>

  <p align="center">
    <a href="https://github.com/ChiyunNoh/GaRLIO"><img src="https://img.shields.io/badge/-C++-blue?logo=cplusplus" /></a>
    <a href="https://github.com/ChiyunNoh/GaRLIO"><img src="https://img.shields.io/badge/Linux-FCC624?logo=linux&logoColor=black" /></a>
    <a href="https://arxiv.org/abs/2502.07703"><img src="https://img.shields.io/badge/Paper-pdf-<COLOR>.svg?style=flat-square" /></a>
    </a>
  </p>
  
  <p align="center">
    <a href="https://rpm.snu.ac.kr"><strong>Jung Hyundo</strong></a>
    ·
    <a href="https://rpm.snu.ac.kr"><strong>Gon-Woo Kim</strong></a>
    <br/>
    <a href="https://www.irl-cbnu.com/"><strong>Intelligent Robotics Lab (IRL)</strong></a>
  </p>

  <h3 align="center"><a href="https://jkros.org/xml/44009/44009.pdf">Paper</a> | <a href="https://youtu.be/">Video</a></h3>
  <div align="center"></div>
</p>

This repository contains the code for GGSLAM: An Object-Level SLAM System Using Gaussian Grouping and Splatting 

<!-- TABLE OF CONTENTS -->
<details open="open" style='padding: 10px; border-radius:5px 30px 30px 5px; border-style: solid; border-width: 1px;'>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#abstract">Abstract</a>
    </li>
    <li>
      <a href="#installation">Installation</a>
    </li>
    <li>
      <a href="#citation">Citation</a>
    </li>
    <li>
      <a href="#Acknowledgement">Acknowledgement</a>
    </li>
  </ol>
</details>


## Abstract

<details>
  <summary>click to expand</summary>
Simultaneous Localization and Mapping (SLAM) is crucial for applications such as autonomous driving, robot navigation, and 3D reconstruction. With advancements in Virtual Reality (VR) and Augmented Reality (AR), the demand for immersive and realistic experiences is increasing. This paper introduces a real-time SLAM system enhanced with object-level information using Gaussian Grouping, based on the Gaussian Splatting technique. Our system utilizes predefined masks generated
by Tracking Anything to segment objects effectively, enabling the real-time construction of high-quality 3D maps. By applying Gaussian Grouping, the system efficiently identifies static objects while integrating object-level data, maintaining the accuracy of traditional Gaussian Splatting-based SLAM. Experimental results demonstrate the system’s high accuracy and efficiency across various environments, enhancing object recognition and interaction for robots, as well as enabling natural interactions with virtual objects in VR/AR applications. This study advances SLAM technologies by providing a high-quality 3D reconstruction method that incorporates object-level information, expanding its applicability to diverse domains. </details>

## Installation
Install requirements
```bash
conda create -n gsicpslam python==3.9
conda activate gsicpslam
conda install pytorch==2.0.0 torchvision==0.15.0 torchaudio==2.0.0 pytorch-cuda=11.8 -c pytorch -c nvidia
pip install -r requirements.txt
```
Also, PCL is needed for fast-gicp submodule.

Install submodules

```bash
conda activate gsicpslam
pip install submodules/diff-gaussian-rasterization
pip install submodules/simple-knn

cd submodules/fast_gicp
mkdir build
cd build
cmake ..
make
cd ..
python setup.py install --user
```


## Citation
```
@article{ Jeong Hyun-do2025gg,
    AUTHOR = { Jung Hyundo and Gon-Woo Kim },
    TITLE = { GGSLAM: An Object-Level SLAM System Using Gaussian Grouping and Splatting},
    JOURNAL={Robot Society Journal},
    volume={20},
    number={1},
    pages={84--93},
    YEAR = { 2025 },
    MONTH = { May. },
    ADDRESS = {SOUTH KOREA},
}
```

## Acknowledgement

Many thanks to GS-ICP SLAM Team— [Seongbo Ha][alink], [Jiung Yeon][blink], [Hyeonwoo Yu]— for provide codes!

Please refer to [GS-ICP-SLAM][gsicplink] for more information

[alink]: https://riboha.github.io
[blink]: https://humdrum-balance-b8f.notion.site/Jiung-Yeon-6754922a22814c9a95af88801a96fb4b
[merschlink]: https://github.com/benemer
[gsicplink]: https://github.com/PRBonn/kiss-icp
