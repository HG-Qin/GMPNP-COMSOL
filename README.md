# GMPNP-COMSOL

This repository contains a COMSOL tutorial for building GMPNP

## The function of the GMPNP model

modeling the cation effect on HER in the solution of 0.01M HClO4 + 10mM LiClO4  by solving the general modified Poisson-Nerst-Planck (GMPNP) equation

## Mathematical description of GMPNP model

1) Geometry (1D)

![image](https://user-images.githubusercontent.com/117021555/198882301-0a9a6ff0-23ae-4a97-acf3-f65a16cb90ba.png)


2) Physics


- modified Nerst Planck equation

![image](https://user-images.githubusercontent.com/117021555/198883265-1b86c98b-2969-429b-8087-7becb761bc1f.png)


- Poisson equation
 
![image](https://user-images.githubusercontent.com/117021555/198882973-dafb95fd-a0d9-4b9a-b3af-c83b18fed03f.png)



## COMSOL tutorial for building GMPNP


![Model builder](https://user-images.githubusercontent.com/117021555/200847887-9036ca52-2161-47f5-b8f8-61a80a19095f.png)

### step 1. Bulid the framwork of Model

- click File->New->Select Space Dimension (1D)->Select Physics (two General Form PDE (g))

![Add physics](https://user-images.githubusercontent.com/117021555/200848691-55a4db09-687e-47c6-9aad-8fd064c17669.png)

- click Done.
- Select Stationary

![Study](https://user-images.githubusercontent.com/117021555/200849243-efe4d564-e4cc-4be6-81f0-2ddf61ca10a7.png)

- click Done. The following is the framwork of the GMPNP model

![Model Builder - new](https://user-images.githubusercontent.com/117021555/200849608-e266789e-59cb-4a44-b2ef-4225de20aa23.png)



