---
layout: page
title: Unreal Robotics Lab (URLab)
description: >-
  An open-source Unreal Engine 5 plugin that embeds the MuJoCo physics engine
  for high-fidelity, photorealistic robotics simulation, sim-to-real transfer,
  and synthetic data generation.
img: assets/img/url_hero.png
importance: 1
category: work
related_publications: true
github: https://github.com/URLab-Sim/UnrealRoboticsLab
github_stars: URLab-Sim/UnrealRoboticsLab
docs: https://urlab-sim.github.io/UnrealRoboticsLab/
arxiv: https://arxiv.org/abs/2504.14135
---

<div class="row justify-content-sm-center">
  <div class="col-sm-12 mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/url_hero.png" title="Unreal Robotics Lab -- MuJoCo physics in Unreal Engine 5" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

**Unreal Robotics Lab (URLab)** is an open-source Unreal Engine 5 plugin that
embeds the [MuJoCo](https://github.com/google-deepmind/mujoco) physics engine
directly into the editor and runtime, combining Unreal's photorealistic
rendering with MuJoCo's precision physics. It targets sim-to-real transfer,
synthetic data generation, and robot learning workflows that need both visual
fidelity and accurate contact dynamics.

- **Code:** [github.com/URLab-Sim/UnrealRoboticsLab](https://github.com/URLab-Sim/UnrealRoboticsLab)
- **Docs:** [urlab-sim.github.io/UnrealRoboticsLab](https://urlab-sim.github.io/UnrealRoboticsLab/)
- **Paper (ICRA 2026):** [arxiv.org/abs/2504.14135](https://arxiv.org/abs/2504.14135)
- **License:** Apache 2.0

## Key features

- **MJCF drag-and-drop import** -- drop a MuJoCo `.xml` into the Content
  Browser and URLab builds a full body / joint / actuator / sensor tree as an
  Articulation Blueprint.
- **Quick Convert** -- attach `UMjQuickConvertComponent` to any Static Mesh and
  it becomes a MuJoCo physics body. No XML required.
- **40+ sensors, 8 actuator types, 4 joint types** -- position, velocity,
  motor, muscle, damper, adhesion, cylinder, general actuators; hinge, slide,
  ball, free joints; accelerometer, gyro, force/torque, touch, rangefinder,
  frame tracking, cameras.
- **ZMQ networking** -- stream sensor data out, receive actuator commands in,
  drive the simulator from Python, ROS 2, or any ZMQ-speaking process.
- **Python policy bridge** -- companion package
  [`urlab_bridge`](https://urlab-sim.github.io/UnrealRoboticsLab/guides/policy_bridge/)
  for remote control, RL policy deployment, and ROS 2 bridging.
- **Record and replay** -- capture trajectories, replay frame by frame,
  CSV import, snapshot and restore full simulation state.
- **MjSimulate dashboard** -- in-editor widget with physics parameter tuning,
  actuator sliders, sensor readouts, live camera feeds.
- **Keyframe system, possession, cinematic tools, CoACD convex decomposition,
  heightfield terrain from Unreal Landscape** -- see the docs for the
  complete feature list.

## When to use URLab

- You need photorealistic rendering with accurate contact physics (sim-to-real
  transfer, synthetic data generation).
- You want to control MuJoCo robots from Python or ROS 2 while rendering in
  Unreal Engine.
- You want Unreal's ecosystem (Blueprints, Sequencer, Marketplace assets,
  Niagara) with physics-accurate robots.

## Requirements

Unreal Engine 5.7+, Windows (Linux experimental), MuJoCo 3.7+ (bundled),
Visual Studio 2022, CMake 3.24+. See the
[Getting Started](https://urlab-sim.github.io/UnrealRoboticsLab/getting_started/)
guide for a full walkthrough.

## Citation

If URLab supports your research, please cite the ICRA 2026 paper:

```bibtex
@inproceedings{embleyriches2026urlab,
  title     = {Unreal Robotics Lab: A High-Fidelity Robotics Simulator with Advanced Physics and Rendering},
  author    = {Embley-Riches, Jonathan and Liu, Jianwei and Julier, Simon and Kanoulas, Dimitrios},
  booktitle = {IEEE International Conference on Robotics and Automation (ICRA)},
  year      = {2026},
  url       = {https://arxiv.org/abs/2504.14135}
}
```

_Unreal Robotics Lab is an independent software plugin. It is NOT affiliated
with, endorsed by, or sponsored by Epic Games, Inc. "Unreal" and "Unreal
Engine" are trademarks of Epic Games, Inc._
