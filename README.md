# GMPNP-COMSOL

This repository contains a COMSOL tutorial to reproduce the GMPNP models in the article "[Quantitative Understanding of Cation Effects on the Electrochemical
Reduction of CO2 and H+ in Acidic Solution](https://pubs.acs.org/doi/10.1021/acscatal.2c04875?ref=pdf)" 

## The function of the GMPNP model

modeling the cation effect on HER in a rotation disk electrode (RDE, 1600rpm) in the solution of 10mM HClO4 + xmM MClO4
## Mathematical description of GMPNP model

1) Geometry (1D)

![image](https://user-images.githubusercontent.com/117021555/198882301-0a9a6ff0-23ae-4a97-acf3-f65a16cb90ba.png)


2) Physics


- modified Nerst Planck equation

![image](https://user-images.githubusercontent.com/117021555/198883265-1b86c98b-2969-429b-8087-7becb761bc1f.png)


- Poisson equation
 
![image](https://user-images.githubusercontent.com/117021555/198882973-dafb95fd-a0d9-4b9a-b3af-c83b18fed03f.png)



## COMSOL tutorial for building GMPNP

### PART A: GMPNP for Au 10mM HClO4 + 10mM LiClO4


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

- The parameter, equations used in PART A can be seen under the folder "para_Au_10mMHClO4_10mMLiClO4"

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

- input Poisson equation, equation text can be seen in equation_Au_10mMHClO4_10mMLiClO4.txt

![Poisson_equation](https://user-images.githubusercontent.com/117021555/200859099-c060066f-3468-4aec-adc4-21c2f4533dff.png)

- set the right boundary condition

![Poisson_Dbc](https://user-images.githubusercontent.com/117021555/200860386-9ecd1801-f75f-41e7-87f8-c7b433e0a8d2.png)

- set the left boundary condition

![Poisson_OHP_bc](https://user-images.githubusercontent.com/117021555/200861196-703f365f-7f0f-4c04-8910-c917cb9d8360.png)


### step 6. Build Modified Nernst-Planck equation

- set Units and Dependent Variables

![Modified NP_var](https://user-images.githubusercontent.com/117021555/200862344-48244543-9a39-4ea5-af20-04203ddd730c.png)

- input Modified NP equation, equation text can be seen in equation_Au_10mMHClO4_10mMLiClO4.txt

![Modified NP_equation](https://user-images.githubusercontent.com/117021555/200862929-867e4497-24e7-4571-b42e-1f45adaa0af2.png)

- set the initial values

![Modified_NP_initial_values](https://user-images.githubusercontent.com/117021555/200865134-136e52e5-1359-4cb8-a5cc-5f8e273e617c.png)

- set the right boundary condition

![Modified_NP_Dbc](https://user-images.githubusercontent.com/117021555/200865693-fd3c1566-f94e-4446-ab82-8a555e582e45.png)

- set the left boundary condition

![Modified_NP_OHP_bc](https://user-images.githubusercontent.com/117021555/200866135-24ac0d1e-bdf1-4038-9208-62ecabcb09b3.png)


### step 7. set mesh

![mesh](https://user-images.githubusercontent.com/117021555/200867083-0bd624bc-2603-49fd-92fb-cf3bb3cc0738.png)


### step 8. set phiM values in Study

- phiM for Au: range(-0.3,-0.05,-2)
- phiM for Ag: range(0.5,-0.05,-1.5)

![Study_phiM](https://user-images.githubusercontent.com/117021555/200867825-158e635d-373b-4578-9c89-80139c29b080.png)

- click compute. It takes 20 minutes for a laptop with a i7-11800H CPU

### step 9. Data output

- set the output mesh

![output_mesh](https://user-images.githubusercontent.com/117021555/200869902-2f5bf08a-9d9a-4847-a17a-e0cf4034f018.png)

- set output parameters

- note: the following graph shows tree kind of parameters, and their expressions can be seen in output_Au_10mMHClO4_10mM_LiClO4.txt:

1. phiM-j: the HER current density vs electrode potential, x = 0

2. xxx-om: variables in domain, x = output_mesh

3. sigma_s: surface charge density, integral on whole domain

![output para](https://user-images.githubusercontent.com/117021555/200870686-9b47a4c1-c56b-437a-a7d3-800dc095cad9.png)

![rho_s](https://user-images.githubusercontent.com/117021555/200872305-ef55ce06-11e3-41f8-b911-707242957021.png)

### PART B: GMPNP for Au 10mM HClO4 + xmM LiClO4 (cation concentration effect on HER)

cation concentration study can be easily realized by modifing the model built in PART A

- step 1: change the parameters, parameter files can be seen in the folder "para_Au_cation_concentration"

![Au cLi Step1](https://user-images.githubusercontent.com/117021555/201667892-e04492ed-dd5d-436b-bb28-74634fba0343.png)


- step 2: change mesh expression. The mesh structrue is extremely important to get a convergence result!
The mesh expression can be seen in para_Au_cation_concentration/mesh_Au_10mMHClO4_xmMLiClO4.txt

![Au cLi step22222](https://user-images.githubusercontent.com/117021555/201669617-027433a7-0c60-4cf7-ae2e-2447094fd354.png)


- step 3: re-edit the phiM values in Study, click compute

![Au cLi Step2](https://user-images.githubusercontent.com/117021555/201668060-36b212df-d44a-4da6-86a2-fbd764b05af1.png)



### PART C: GMPNP for Au 10mM HClO4 + 10mM MClO4 (cation identity effect on HER)

follow the step in PART A, but use the corresponding parameters, variables, equations, mesh under the folder "Au_cation_identity"

- change the name of the dependent variable cLi to corresponding name (cNa, cK, cCs)

![note cation identity](https://user-images.githubusercontent.com/117021555/201683339-b0d8b58c-15e6-491c-a983-3b784965852b.png)


### PART D: GMPNP for Au 10mM HClO4

follow the step in PART A, but use the corresponding parameters, variables, equations, mesh under the folder "para_Au_10mMHClO4"

- only three dependent variables in Modified NP

![PART D](https://user-images.githubusercontent.com/117021555/201690651-50b6dbdb-ee16-42ce-96a0-beb09be5052e.png)


### PART E: GMPNP for Ag 10mM HClO4 + xmM MClO4

similar to PART A-C, but use the parameter, mesh under the folder "para_Ag_cation_concentration" or "para_Ag_cation_identity"

- phiM values for Study is range(0.5,-0.05,-1.5)

![PART_E](https://user-images.githubusercontent.com/117021555/201694747-91ced3bd-8861-425c-911f-e698658e4349.png)


- convergence problem: Ag 10mM HClO4 can converge to -1.5V, while Ag 10mM HClO4 + xmM MClO4 can only converge to around -1V


#### PART F: GMPNP for the relative permittivity varied with cation concentration

It can be realized by modifying the GMPNP model with constant relative permittivity.

- delect the epsilon_r(80.1) in Parameters

![PART F parameters](https://user-images.githubusercontent.com/117021555/201814718-6381c4da-dedb-4d85-9193-5ccd8d004aa0.png)


- take 10mM HClO4+ 10mM LiClO4 as example, add w_H, w_Li, M_water, epsilon_r_0, epsilon_r_min into Parameters, see equation in PDF file under the folder "relative permittivity"

![PART F parameters add](https://user-images.githubusercontent.com/117021555/201815939-11ebd6b3-a54e-44a3-a1ad-4955bdf18aea.png)

- add the expression of variable epsilon_r in Variables Domain

![PART F variable](https://user-images.githubusercontent.com/117021555/201816951-1cff6cf8-6e3f-4dfa-9c38-7bead0e8238a.png)

- set mesh. the expression can be seen in relative permittivity/mesh.txt

![PART F mesh](https://user-images.githubusercontent.com/117021555/201817724-6d3c928e-df55-4ac0-a01f-908c6a9f1e92.png)


- convergence problems: GMPNP model with variable relative permittivity of water has more poor convergence performance than that with constant relative permittivity






