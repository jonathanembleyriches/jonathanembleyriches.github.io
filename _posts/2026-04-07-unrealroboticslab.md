---
layout: post
title: "Announcing Unreal Robotics Lab (URLab) -- MuJoCo Physics in Unreal Engine 5"
date: 2026-04-07 15:40:00
description: >-
  Alpha release of Unreal Robotics Lab (URLab), an open-source Unreal Engine 5
  plugin that embeds the MuJoCo physics engine for high-fidelity,
  photorealistic robotics simulation and sim-to-real research.
tags:
  - Unreal-Robotics-Lab
  - URLab
  - UnrealRoboticsLab
  - MuJoCo
  - Unreal-Engine
  - UE5
  - robotics
  - simulation
  - sim2real
  - synthetic-data
  - reinforcement-learning
  - ROS2
categories: robotics simulation open-source
thumbnail: assets/img/url_hero.png
giscus_comments: false
featured: true
related_publications: true
---

I'm excited to share the alpha release of **Unreal Robotics Lab (URLab)** --
an open-source Unreal Engine 5 plugin that embeds the
[MuJoCo](https://github.com/google-deepmind/mujoco) physics engine directly
into the editor and runtime.

{% include figure.liquid loading="eager" path="assets/img/url_hero.png" title="Unreal Robotics Lab -- MuJoCo in Unreal Engine 5" class="img-fluid rounded z-depth-1" %}

**TL;DR.** URLab combines Unreal Engine's photorealistic rendering with
MuJoCo's precision physics, targeting sim-to-real transfer, synthetic data
generation, and robot learning workflows that need both visual fidelity and
accurate contact dynamics.

- **Code (Apache 2.0):** [github.com/URLab-Sim/UnrealRoboticsLab](https://github.com/URLab-Sim/UnrealRoboticsLab)
- **Documentation:** [urlab-sim.github.io/UnrealRoboticsLab](https://urlab-sim.github.io/UnrealRoboticsLab/)
- **Paper (ICRA 2026):** [arXiv:2504.14135](https://arxiv.org/abs/2504.14135)
- **Announcement:** [X / Twitter](https://x.com/JonEmbleyRiches/status/2041541672543064361) &middot; [LinkedIn](https://www.linkedin.com/posts/jonathan-embley-riches_im-excited-to-share-the-alpha-release-of-activity-7447305621978263552-2aEo)

## Why URLab

Most robotics simulators force a trade-off: fast, accurate physics _or_
photorealistic rendering. URLab removes that trade-off by running MuJoCo on an
async physics thread inside Unreal Engine 5, with a component-based
architecture that maps 1:1 to MuJoCo elements. You get the full MuJoCo C API
from C++ and Blueprints, MJCF drag-and-drop import, and ZMQ networking to
drive the sim from Python or ROS 2 -- all inside Unreal's editor.

## What's in the alpha

- **MJCF drag-and-drop import** -- drop a MuJoCo `.xml` into the Content
  Browser and URLab builds a full body / joint / actuator / sensor tree as an
  Articulation Blueprint.
- **Quick Convert** -- attach a component to any Static Mesh and it becomes a
  MuJoCo physics body. No XML required.
- **40+ sensors, 8 actuator types, 4 joint types** -- covering position,
  velocity, motor, muscle, damper, adhesion, cylinder, general actuators;
  hinge, slide, ball, free joints; accelerometer, gyro, force/torque, touch,
  rangefinder, frame tracking, cameras.
- **ZMQ networking** -- stream sensor data out and receive actuator commands
  in via PUB/SUB sockets.
- **Python policy bridge** (`urlab_bridge`) -- remote control, RL policy
  deployment, sensor monitoring, ROS 2 bridging.
- **Record and replay**, **keyframe system**, **possess-and-walk** control,
  **cinematic tools**, **CoACD convex decomposition**, **Unreal Landscape ->
  MuJoCo heightfield** conversion.
- **MjSimulate dashboard** -- in-editor widget with physics tuning, actuator
  sliders, live sensor readouts and camera feeds.

## When to use it

- You need photorealistic rendering _with_ accurate contact physics --
  sim-to-real transfer, synthetic data generation for perception models.
- You want to control MuJoCo robots from Python or ROS 2 while rendering in
  Unreal Engine.
- You want Unreal's ecosystem (Blueprints, Sequencer, Marketplace assets,
  Niagara) paired with physics-accurate robots.

## Getting started

```bash
cd YourUnrealProject/Plugins
git clone https://github.com/URLab-Sim/UnrealRoboticsLab.git
cd UnrealRoboticsLab/third_party
./build_all.ps1
```

Regenerate project files, build, launch the editor, and drop an MJCF into the
Content Browser. Full walkthrough in the
[Getting Started guide](https://urlab-sim.github.io/UnrealRoboticsLab/getting_started/).

Requirements: Unreal Engine 5.7+, Windows (Linux experimental), MuJoCo 3.7+
(bundled), Visual Studio 2022, CMake 3.24+.

## Citing URLab

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

## Getting involved

Issues, discussions, and contributions are welcome on
[GitHub](https://github.com/URLab-Sim/UnrealRoboticsLab). If you're building
on URLab or considering it for a project, I'd love to hear about it -- reach
out via the contact links on the homepage or drop a note in the repo's
[Discussions](https://github.com/URLab-Sim/UnrealRoboticsLab/discussions).

_Unreal Robotics Lab is an independent software plugin. It is NOT affiliated
with, endorsed by, or sponsored by Epic Games, Inc. "Unreal" and "Unreal
Engine" are trademarks of Epic Games, Inc._
