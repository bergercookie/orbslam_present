<!-- .slide: class="center" -->
## Presentation on ORB-SLAM

<div style="color:gray; font-size: 1.3em">
Nikos Koukis<br>
</div>

---

## Presentation Contents

- Presenter Information and Background
- ORB-SLAM:
  - Overview
  - Tracking
  - Local Mapping
  - Loop Detection
  - Q&A


---

<!-- .slide: class="center" -->
## Presenter Information and Background

note:
The whole "Talk about you" should be about ~5min
Practice.

---

#### Presenter Information and Background

<div style="font-size:0.8em">
<ul>
  <li>Nikos Koukis
  <ul>
  <li> 5yr Diploma in Mechanical Engineering - [National Technical university of Athens (NTUA)](www.mech.ntua.gr/en)</li>
  <ul>
    <li> Specialization in "Mechanical Design and Automatic Control"</li>
    <li>Thesis</li>
    <ul>
      <li>  Laboratory of Automatic Control & Machine and Plant Regulation</li>
      <li>  Supervisor: Prof. Kostas J. Kyriakopoulos</li>
      <li>  Subject: *Investigation, Design, and Development of Single and Multi-robot SLAM algorithms*</li>
  </ul>
  </ul>
</ul>
</div>

---

#### Presenter Information and Background

<div style="font-size:0.8em">
<ul>
  <li>**2016 - GSoC Internship @MRPT:**<br>[Design and development of a full graph-based SLAM strategy](https://summerofcode.withgoogle.com/archive/2016/projects/6025600208732160/)
  <li>  Complete Graph-based SLAM framework
  <ul>
    <li> Generic/Modular design
    <li> Offline/Real-time use
    <li> 2D laser scans (use of ICP), optionally odometry
  </ul>
  <li> Robust Loop-Closure scheme - E.  Olson
  <li> SLAM Error metric and visualization - C. Stachniss
  <li> **2017 - GSoC Mentoring @MRPT:**<br>[Robust SLAM using fiducial markers and stereo vision](https://github.com/MRPT/GSoC2017-discussions/issues/5)
</ul>
</div>

---?image=assets/figures/bulk/gui_main.png&size=contain
<!-- .slide: data-background-transition="none" -->
---?image=assets/figures/bulk/real_time_CFixedIntervalsNRD_CLoopCloserERD_gt.png&size=contain
<!-- .slide: data-background-transition="none" -->

---

#### Presenter Information and Background

Extend algorithm to work with multiple robots

<div style="font-size:0.8em">
<ul>
<li>Unknown starting agent positions</li>
<li>Arbitrary number of agents</li>
<li>Robust to communication, agent failure</li>
<li>Minimization of exchanged data between agents - Assume limited communications</li>
</ul>
</div>

<hr>

<div style="font-size:0.8em">
<ul>
  <li>Fully distributed ad-hoc network</li>
  <li>Compute inter-robot frame transformation</li>
    <ul>
      <li>Multi-hypothesis map-matching</li>
      <li>Visual technique: Use of Harris Corners + Linear/Log Circular Patch descriptor</li>
    </ul>
</ul>
</div>

---

<!-- .slide: class="center" -->
## Simulation with 3 agents

---?image=assets/figures/bulk/map_merger_node_3_robots.png&size=contain

---?image=assets/figures/bulk/gazebo_simulation_env_more_obstacles.png&size=contain
<!-- .slide: data-background-transition="none" -->
---?image=assets/figures/bulk/simulation_map_match_more_obstacles.png&size=contain
<!-- .slide: data-background-transition="none" -->

---

<!-- .slide: class="center" -->
### Experiment - Around the pool

---?image=assets/figures/bulk/online_integration_nickkoukubuntu2.png&size=contain

---

<!-- .slide: class="center" -->
# ORB-SLAM

---

### Why choose ORB-SLAM?

<div style="font-size:0.8em">
<ul>
  <li> Authors build **incrementally** on their previous works, other recent Visual-SLAM techniques</li>
  <ul>
    <li> BoW (Bag of Words)</li>
    <li> DBoW2</li>
    <li> ORB:</li>
    <ul>
      <li> Multiscale FAST detector</li>
      <li> Rotation-invariant BRIEF</li>
    </ul>
    <li> ORB-SLAM</li>
    <li> ORB-SLAM 2 (Stereo, RGB-D)</li>
  </ul>
  <li> Offer complete solution in camera-based SLAM</li>
  <ul>
    <li> Tracking, Relocalization, Mapping, Map initialization, Loop-Closing, 3D Reconstruction (ORB-SLAM2)</li>
  </ul>
</ul>
</div>

---

### Overview

- Mur-Artal, Montiel, Tardos ~2015
- Feature-based method
- Uses ORB Features
- Based on PTAM (Parallel Tracking and Mapping)
- Supports multiple input sources
- Exhaustive testing on well-known datasets
- Comparison with relevant works (LSD-SLAM, SVO, etc.)
- Open-source

---

### Main features

- Same set of features (ORB) for all tasks |
- Large-scale, real-time, lifelong operation |
- Loop closing via the Essential Graph |
- Camera relocalization |
- Automatic Initialization procedure |
  - Planar |
  - Non-planar movement  |

---

<!-- .slide: class="center" -->
## Automatic Map Initialization

##### Compute relative pose between two frames

---

## Tracking

- ORB Extraction
- Pose estimation
  - Previous frame
  - Global relocalization
- Track Local Map
- New KF decision


---

## Local Mapping

- KF Insertion
- Recent Map Points Culling
- New Map Point Creation
- Local BA
- Local KF Culling


---

## Loop Closing

- Loop Detection Candidates
- Compute Similarity Transform
- Loop Fusion
- Essential Graph Optimization

---

<!-- .slide: class="center" -->
## Q&A
## Discussion
