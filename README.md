# Accelerometer sensor dataset for Human Posture Recognition

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

<img src="https://github.com/pkmandke/Human-Posture-Dataset/blob/master/img/sample_pose.png" alt="https://github.com/pkmandke/Human-Posture-Dataset/blob/master/img/sample_pose.png" height="75%"></img>


This repository links to the dataset that we created during [our work](https://ieeexplore.ieee.org/document/8692143) on Human Posture Recognition at [College of Engineering, Pune](http://www.coep.org.in/) in the Spring of 2018. The dataset consists of accelerometer sensor values for 6 postures namely - standing, sitting, sleeping, running, forward bending and backward bending - from the Invensense' MEMS IMU sensor [MPU-6050](https://www.invensense.com/products/motion-tracking/6-axis/mpu-6050/) mounted one each on the left chest and the right thigh.

The dataset is in the form of a single csv file of size 3.2MB. [Download](https://drive.google.com/open?id=1GtNRi9CgHOlGpsa-Dlp6uzAqXUVdEh54).

# Data Summary

| Posture | Number of samples |
|---|---|
| Sleeping | 8329 |
| Standing | 8358 |
| Sitting | 7542 |
| Running | 3617 |
| Forward Bending | 11504 |
| Backward Bending | 5450 |
| **Total** | **44800**  |

# Details

<img src="https://github.com/pkmandke/Human-Posture-Dataset/blob/master/img/b_diag.png" alt="https://github.com/pkmandke/Human-Posture-Dataset/blob/master/img/b_diag.png"/>

## Data

The csv file has a total of 44800 samples each having 6 columns. The **Ax1, Ay1 and Az1** are the accelerometer readings from the **chest sensor** while **Ax2, Ay2 and Az2** are the readings from the **thigh sensor**. The readings are not calibrated or filtered and contain any noise as is. The last column of labels identifies the corresponding posture. The posture legend is as follows:

| Label | Posture |
|---|---|
|0| Sleeping |
| 1| Standing |
| 2 | Sitting |
| 3| Running |
| 4| Forward Bending |
| 5| Backward Bending|

## Nuances


The data has been collected from a total of 3 subjects who were students at [College of Engineering, Pune](http://www.coep.org.in/). Note that the readings for a given posture from all 3 subjects have been combined and are indistinguishable. Please [contact us](https://github.com/pkmandke/Human-Posture-Dataset#authors) if you need the readings of each subject and posture separately.

We encourage you to shuffle the data for a single posture for robustness during training a classifier. Moreover, the number of readings for each posture and subject are not the same. This is because of 2 reasons. Firstly, we removed outliers from each data collection session. Secondly, it was difficult to maintain the same postures for long periods of time and we ensured the comfort of the subjects.

<img src="https://github.com/pkmandke/Human-Posture-Dataset/blob/master/img/sensor_node.png" alt="https://github.com/pkmandke/Human-Posture-Dataset/blob/master/img/sensor_node.png"></img>

In order to collect the data, we built a small PCB to interface the MPU-6050 with the Espressif's ESP8266 based [NodeMCU](https://www.nodemcu.com/index_en.html) and deployed the sensor on the human subjects as shown above. The data was then wirelessly transmitted from the NodeMCU to a central node interfaced serially with a PC where the readings were sampled at **200ms intervals**. HTTP was used over TCP/IP for the data transfer to and from the NodeMCU.

During the static postures, the subjects were directed to include slight natural movements which make the readings more robust for training classifiers. For the bending postures, the subjects were in sitting position and bent forward and backward at 30-40 degrees to the vertical. For running, the subjects jogged in the same place for the most part with slight translational motion or displacement occasionally. Thus, the readings for running are spurious at best.

For more details, refer to our paper [here](https://ieeexplore.ieee.org/document/8692143). Feel free to [contact us](https://github.com/pkmandke/Human-Posture-Dataset#authors) for further queries.

## Data visualization

<img src="https://github.com/pkmandke/Human-Posture-Dataset/blob/master/img/sleephist.png" alt="https://github.com/pkmandke/Human-Posture-Dataset/blob/master/img/sleephist.png"></img>

Scripts in the form of ipython notebooks that vizualize the data and also train sample classifiers will be released soon. Stay tuned!

# Citation

If you use our dataset in your work, please cite [our paper](https://ieeexplore.ieee.org/document/8692143).

H. Kale, P. Mandke, H. Mahajan and V. Deshpande, "Human Posture Recognition using Artificial Neural Networks," 2018 IEEE 8th International Advance Computing Conference (IACC), Greater Noida, India, 2018, pp. 272-278.

# Authors

* [Prathamesh Mandke](https://www.linkedin.com/in/prathamesh-mandke-866866168/) - pkmandke AT vt DOT edu

  I am the maintainer of this repository. Please raise an issue or email me for questions.

* [Hrishikesh Kale](https://www.linkedin.com/in/hrishikesh-kale-02b338140/) - kalehp15 DOT extc AT coep DOT ac DOT in
* [Hrishikesh Mahajan](https://www.linkedin.com/in/hrishikeshmahajan3/) - mahajanhs15 DOT extc AT coep DOT ac DOT in
* Vedant Deshpande - deshpandevv16 DOT extc AT coep DOT ac DOT in

# License

TL;DR - Feel free to use this in your work so long as you cite us!

This dataset is licensed under the GPL license. See [the license](https://github.com/pkmandke/Human-Posture-Dataset/blob/master/LICENSE.md) for details.
