<p align="center">

  <h1 align="center"> GGSLAM: An Object-Level SLAM System Using Gaussian Grouping and Splatting </h1>

  <p align="center">
    <a href="https://github.com/cocel-postech/genz-icp/tree/master/ros"><img src="https://img.shields.io/badge/ROS1-Noetic-blue" /></a>
    <a href="https://jkros.org/xml/44009/44009.pdf"><img src="https://img.shields.io/badge/Paper-pdf-<COLOR>.svg?style=flat-square" /></a>
    <a href="https://youtu.be/"><img src="https://img.shields.io/badge/Video-video-yellow.svg?style=flat-square" /></a>
    </a>
  </p>
  
  <p align="center">
    <strong>Jung Hyundo</strong></a>
    ·
    <a href="https://www.irl-cbnu.com/professor"><strong>Gon-Woo Kim</strong></a>
    <br/>
    <a href="https://www.irl-cbnu.com/"><strong>Intelligent Robotics Lab (IRL)</strong></a>
  </p>

  <h3 align="center"><a href="https://jkros.org/xml/44009/44009.pdf">Paper</a> | <a href="https://youtu.be/">Video</a></h3>
  <div align="center"></div>
</p>

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
Simultaneous Localization and Mapping (SLAM) is crucial for applications such as autonomous driving, robot navigation, and 3D reconstruction. With advancements in Virtual Reality (VR) and Augmented Reality (AR), the demand for immersive and realistic experiences is increasing. This paper introduces a real-time SLAM system enhanced with object-level information using Gaussian Grouping, based on the Gaussian Splatting technique. Our system utilizes predefined masks generated
by Tracking Anything to segment objects effectively, enabling the real-time construction of high-quality 3D maps. By applying Gaussian Grouping, the system efficiently identifies static objects while integrating object-level data, maintaining the accuracy of traditional Gaussian Splatting-based SLAM. Experimental results demonstrate the system’s high accuracy and efficiency across various environments, enhancing object recognition and interaction for robots, as well as enabling natural interactions with virtual objects in VR/AR applications. This study advances SLAM technologies by providing a high-quality 3D reconstruction method that incorporates object-level information, expanding its applicability to diverse domains.

## Installation
### Prerequisited
Follow [FAST-LIVO2][gsicplink] and [GS-ICP Slam][gsicplink].

Install requirements
```bash
conda create -n gsicpslam python==3.9
conda activate gsicpslam
conda install pytorch==2.0.0 torchvision==0.15.0 torchaudio==2.0.0 pytorch-cuda=11.8 -c pytorch -c nvidia
pip install -r requirements.txt
conda activate gsicpslam
```
Also, PCL is needed for fast-gicp submodule.

```bash
mkdir -p gg_ws/src
cd gg_ws/src
git clone https://github.com/dsowrd/Segment-Any-Gaussian-Splatting-SLAM.git

Install submodules

cd Segment-Any-Gaussian-Splatting-SLAM
pip install submodules/diff-gaussian-rasterization
pip install submodules/simple-knn

cd submodules/fast_gicp
mkdir build
cd build
cmake ..
make
cd ..
python setup.py install --user

Build package
cd ~/gg_ws
catkin_make
```


## Citation
```
@article{정현도2025gg,
  title={GG-SLAM: Gaussian Grouping 과 Splatting 을 이용한 객체 수준 SLAM 시스템},
  author={정현도 and 김곤우},
  journal={로봇학회 논문지},
  volume={20},
  number={1},
  pages={84--93},
  year={2025}
}
```

## Acknowledgement

Many thanks to [GS-ICP-SLAM][gsicplink] and [FAST-LIVO2][fastlivo2link]!

[gsicplink]: https://github.com/Lab-of-AI-and-Robotics/GS_ICP_SLAM
[fastlivo2link]: https://github.com/hku-mars/FAST-LIVO2
