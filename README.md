# GMPNP-COMSOL

This repository contains a COMSOL tutorial for building GMPNP

## The function of the GMPNP model

modeling the cation effect on HER in a rotation disk electrode (RDE, 1600rpm) in the solution of 0.01M HClO4 + 10mM LiClO4  by solving the general modified Poisson-Nernst-Planck (GMPNP) equation

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

- click Study
- select Stationary

![Study](https://user-images.githubusercontent.com/117021555/200849243-efe4d564-e4cc-4be6-81f0-2ddf61ca10a7.png)

- click Done. The following is the framwork of the GMPNP model

![Model Builder - new](https://user-images.githubusercontent.com/117021555/200849608-e266789e-59cb-4a44-b2ef-4225de20aa23.png)

### step 2. Import parameters

![input para](https://user-images.githubusercontent.com/117021555/200851487-93c60912-8f96-49a0-b3bd-4a9238457842.png)

### step 3. Import variables

![var_OHP](https://user-images.githubusercontent.com/117021555/200855128-9d09a78e-d395-464e-8ebc-69acb0d3b885.png)
![var_Domain](https://user-images.githubusercontent.com/117021555/200855172-8cc1a4c6-05f1-4968-8ba5-d77908658964.png)

### step 4. Build geometry

![Geo1](https://user-images.githubusercontent.com/117021555/200856283-20f42bec-310e-461c-b960-4cd09aa8c08d.png)

![Geo2](https://user-images.githubusercontent.com/117021555/200856827-0c24995f-c6b8-48b8-a926-0df17e6a1730.png)

### step 5. Build Poisson equation
- rename the General Form PDE Physic as Poisson and Modified NP
- set Units and Dependent Variables

![Poisson_name_Units](https://user-images.githubusercontent.com/117021555/200858501-4889f85f-2706-424d-8385-ea04f8dae3e5.png)

- input Poisson equation

![Poisson_equation](https://user-images.githubusercontent.com/117021555/200859099-c060066f-3468-4aec-adc4-21c2f4533dff.png)

- set the right boundary condition

![Poisson_Dbc](https://user-images.githubusercontent.com/117021555/200860386-9ecd1801-f75f-41e7-87f8-c7b433e0a8d2.png)

- set the left boundary condition

![Poisson_OHP_bc](https://user-images.githubusercontent.com/117021555/200861196-703f365f-7f0f-4c04-8910-c917cb9d8360.png)


### step 6. Build Modified Nernst-Planck equation

- set Units and Dependent Variables

![Modified NP_var](https://user-images.githubusercontent.com/117021555/200862344-48244543-9a39-4ea5-af20-04203ddd730c.png)

- input Modified NP equation

![Modified NP_equation](https://user-images.githubusercontent.com/117021555/200862929-867e4497-24e7-4571-b42e-1f45adaa0af2.png)

- set the initial values





