# Physics-guided diffusion models

This repository contains the codes for implementing physics-guided diffusion models for inverse design of disordered metamaterials.


## Illustration of phsics-guided diffusion models

<p align="middle">
  <img src="docs/intro.jpg" width="700" />
</p>
<p align="middle">
    <em >Illustration of physics-guided sampling process in diffusion models, where the goal is to achieve target load-displacement response.</em>
</p>

## Key advantages


_Physics consistency_:
    By integrating differentiable physics solvers into the generative process, the approach enables direct steering of the sampling trajectory towards structures that strictly satisfy desired properties, such as specific thermal conductivity, load–displacement response, or energy absorption shown in the diverse case studies in this work. 

_Label-free and solver-decoupled training_:
    The proposed diffusion framework can be trained on unlabeled datasets, avoiding the expensive generation of property labels typically required by conditional generative models. Moreover, by decoupling the physics solver from training and using it only for sampling, the approach avoids repeated solver evaluations and backpropagation across batches and diffusion steps, leading to substantially improved computational efficiency and training stability.    
    
_Flexibility_: 
    The physics-guided approach can be flexibly adapted to a variety of inverse problems simply by modifying the guidance term, as evidenced by its effective performance across all three different design objectives in this work.


## Numerical examples

__Design of effective thermal conductivity__

<p align="middle">
  <img src="docs/k_30.jpg" width="700" />
</p>
<p align="middle">
    <em >Evolution of effective thermal conductivities and sampled structures in the task of designing the effective thermal conductivity.</em>
</p>

__Control of load-displacement response__

<p align="middle">
  <img src="docs/c_mse.jpg" width="700" />
</p>
<p align="middle">
    <em >Evolution of MSE of responses and sampled structures in the task of controlling the load-displacement response.</em>
</p>

__Maximization of energy absorption involving fractures__

<p align="middle">
  <img src="docs/e_evo.jpg" width="700" />
</p>
<p align="middle">
    <em >Evolution of absorbed energy, volume fraction and sampled structures in the task of maximizing the energy absorption.</em>
</p>


## Descriptions

Six separate folders are archived in this repository: __diffusion__ contains the codes of score based diffusion models (training and sampling) and three numerical examples of designing the foam materails, __THERM__ contains the thermal analysis codes, __MECH__ contains the mechanical analysis codes, __experiment__ contains the load-displacement curves, __PF__ contains the phase-field simulation codes, and __foam__ contains the code for generating the foam microstructures. The codes are written in Python and PyTorch.


## Citation

If you found this library useful, we appreciate your support if you consider citing the following paper:

```bibtex
@misc{xie2026physicsguideddiffusionmodelsinverse,
      title={Physics-guided diffusion models for inverse design of disordered metamaterials}, 
      author={Ziyuan Xie and Weipeng Xu and Dazhi Zhao and Wenchang Zhang and Daoyang Dong and Bingbing Xu and Ning Liu and Sheng Mao and Tianju Xue},
      year={2026},
      eprint={2603.16209},
      archivePrefix={arXiv},
      primaryClass={cs.CE},
      url={https://arxiv.org/abs/2603.16209}, 
}
```
