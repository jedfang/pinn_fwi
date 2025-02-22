Physics-guided deep autoencoder
===============================

In this repository, I implemented the physics-informed neural network for full-waveform inversion based on Dhara and Sen (2022). 
The architecture of their study is shown in the following figure. 
 
![architecture](/readme_files/architecture.jpg)

For runing the code, you should use this [notebook](https://github.com/AmirMardan/pinn_fwi/blob/main/pinn_fwi.ipynb).
The required parameters for running this notebook should be set in this [config](https://github.com/AmirMardan/pinn_fwi/blob/main/config.py) file.

<span style='color:red; font-weight:bold;'>Note: </span> I have commented cell 3 in this notebook, you should run this cell whenever you change an acquisition parameter (and for the first time using the codes).

<span style='color:red; font-weight:bold;'>Note: </span> Please use the [requirements](https://github.com/AmirMardan/pinn_fwi/blob/main/requirements.txt) file (written in the jupyter file) to install the packages with specified versions to be sure everything works.
```console
pip install -r requirements.txt
```
The result of running this notebook for three shots is shown in the following figure. 
![res](/readme_files/result_3shots_800.png)

Using 18 shots, result is as following figure.
![res](/readme_files/result_18shots_800.png)

As you see, the networks work properly enough to create the familiar structures of the Marmousi model, but optimum hyperparameters and acquisition parameters should be found.
I have not used the parameters based on the paper.
If you want to reproduce Dhara's work, use the following table.


| Parameter      | Description      |  I used  |  In the paper  |
| ----------- | -----------         |   ------ | -----------    |
| `N_SHOTS`      | Number of shots  |  3       | 18             |
| `DH`   | Spatial sampling         | 5 m      | 1 m            |
| `VP_MIN`| Minimum velocity        | 1450 m/s | 1500 m/s       |
| `VP_MAX`| Maximum velocity        | 4550 m/s | 4700 m/s       |
| `N_RECEIVERS`| Number of receivers| 447      | 200            |
| `ITERATION`| Number of iterations | 800      | 4000           |


Reference:
```
@article{
Physics-guided deep autoencoder to overcome the need for a starting model in full-waveform inversion
Dhara, Arnab and Mrinal K. Sen
The Leading Edge (2022),41(6): 375
https://doi.org/10.1190/tle41060375.1
```