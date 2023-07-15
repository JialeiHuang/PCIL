# README

## Overview

This is codebase for paper [Policy Contrastive Imitation Learning](https://arxiv.org/abs/2307.02829). This codebase is build upon [ROT](https://osf.io/4w69f/?view_only=e29b9dc9ea474d038d533c2245754f0c) .

In this repo, we provide intro to

- get start
- download expert demo
- train agents

## Getting Start

- Install [Mujoco](http://www.mujoco.org/) based on the instructions given [here](https://github.com/facebookresearch/drqv2).

- Installing the following libraries

  ```
  apt install libosmesa6-dev libgl1-mesa-glx libglfw3
  ```

- installing conda environments

  ```
   conda env create -f conda_env.yml
   cd <root_to_pcil_codebase>
   conda activate pcil 
  ```



## Download expert demos

Download expert demonstrations, weights and environment libraries [[link]](https://osf.io/4w69f/?view_only=e29b9dc9ea474d038d533c2245754f0c)
The link contains the following:

- The expert demonstrations for all tasks in the paper.
- The weight files for the expert (DrQ-v2) and behavior cloning (BC).
- The supporting libraries for environments (Gym-Robotics, metaworld) in the paper.
- Extract the files provided in the link
  - set the `path/to/dir` portion of the `root_dir` path variable in `cfgs/config.yaml` to the path of the `PCIL` repository.
  - place the `expert_demos` and `weights` folders in `${root_dir}/PCIL`.

## Load to the logger

We use online logger [WANDB]:(https://wandb.ai), you can customize your own logger in logger.py.

## Train your own agent

We provide an example script:

```
python train.py agent=pc suite=dmc  device_id=0 obs_type=features  suite/dmc_task=hopper_stand  num_demos=10  
```

You can customize more parameters in config files in  ./cfgs

