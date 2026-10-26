# KOUDRUPED in NVIDIA Isaac Lab

![KOUDRUPED in Isaac Sim](media/isaac_robot.png)

This repository brings the **KOUDRUPED** 12-DOF quadruped into **NVIDIA Isaac Sim / Isaac Lab** as the base for **reinforcement-learning-based locomotion**. The goal is to train a walking policy in simulation and later transfer it to the physical robot.

Robot model and Simulink work: [koudruped-control](https://github.com/Eemirhan/koudruped-control)

## Roadmap

- [x] Export the robot as URDF
- [x] Import the URDF into Isaac Lab
- [x] Correct joint frames, axes and angle conventions so the simulated robot matches the physical one
- [ ] Define the locomotion task (observations, actions, rewards)
- [ ] Train a flat-terrain walking policy (PPO)
- [ ] Rough terrain and domain randomisation
- [ ] Sim-to-real tests on the physical robot

## Asset preparation

After importing the URDF, several joints did not match the real robot: some had flipped axes, some had zero positions that differed from the physical calibration, and joint limits had to be set. I corrected these so that the same joint command gives the same leg pose in simulation and on the robot.

<p align="center">
  <img src="media/before_fix.png" width="48%" />
  <img src="media/after_fix.png" width="48%" />
</p>

## Repository structure

| Folder | Content |
|---|---|
| `assets/` | URDF and the converted USD file of the robot |
| `media/` | Screenshots |

## Requirements

NVIDIA Isaac Sim and Isaac Lab, with an NVIDIA RTX GPU.
