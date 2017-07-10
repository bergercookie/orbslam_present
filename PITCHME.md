<!-- .slide: class="center" -->
## Presentation on ORB-SLAM

<div style="color:gray; font-size: 1.3em">
Nikos Koukis<br>
</div>

---

## Presentation Contents

- Presenter Information and Previous Work
- ORB-SLAM:
  - Overview
  - Q&A


---

<!-- .slide: class="center" -->
## Presenter Information and Background

note:
The whole "Talk about you" should be about ~5min
Practice.

---

### Presenter Information and Background

- Nikos Koukis
- 5yr Diploma in Mechanical Engineering
  + [National Technical university of Athens (NTUA)](www.mech.ntua.gr/en)
  + Specialization in "Mechanical Design and Automatic Control"
- Thesis
  + Laboratory of Automatic Control & Machine and Plant
    Regulation
  + Supervisor: Prof. Kostas J. Kyriakopoulos
  + Subject: *Investigation, Design, and Development of Single and Multi-robot
      SLAM algorithms*

---

### Presenter Information and Background

- **2016 - GSoC Internship @MRPT:**<br>[Design and development of a full graph-based SLAM strategy](https://summerofcode.withgoogle.com/archive/2016/projects/6025600208732160/)
  - Complete Graph-based SLAM framework
    - Generic/Modular design
    - Offline/Real-time use
    - 2D laser scans (use of ICP), optionally odometry
  - Robust Loop-Closure scheme - designed by E.  Olson
  - SLAM Error metric and visualization - designed by C. Stachniss
- **2017 - GSoC Mentoring @MRPT:**<br>[Robust SLAM using artificial fiducial markers and stereo vision](https://github.com/MRPT/GSoC2017-discussions/issues/5)


---?image=assets/figures/bulk/gui_main.png&size=contain
<!-- .slide: data-background-transition="none" -->
---?image=assets/figures/bulk/real_time_CFixedIntervalsNRD_CLoopCloserERD_gt.png&size=contain
<!-- .slide: data-background-transition="none" -->

---

### Presenter Information and Background

Extend algorithm to work with multiple robots

- Unknown starting agent positions
- Arbitrary number of agents
- Robust to communication, agent failure
- Minimization of exchanged data between agents - Assume limited communications

<hr>

- Fully distributed ad-hoc network
- Compute inter-robot frame transformation
  - Multi-hypothesis map-matching
  - Visual technique: Use of Harris Corners + Linear/Log Circular Patch descriptor

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
#ORB-SLAM

---

### Overview

% TODO - who did this
% TODO - Where does the algorithm work
% TODO - What's its main features

---

### Why choose ORB-SLAM?

- Authors build **incrementally** on their previous works, other recent
    Visual-SLAM techniques
  - BoW (Bag of Words)
  - DBoW2
  - ORB:
    - FAST detector
    - BRIEF descriptor
  - Rotation-invariant BRIEF
  - ORB-SLAM
  - ORB-SLAM 2 (Stereo, RGB-D work)
- Offer a complete solution in Camera-based SLAM
  - Tracking, Relocalization, Mapping, 3D Reconstruction (ORB-SLAM2),
      Loop-Closing
  - Same set of features (ORB) for all tasks
  - Efficient implementation (via 3 parallel threads)
  - Suppor multiple input sources: Monocular, Stereo, RGB-D (for ORB-SLAM2)
- Very well tested
- Comparative results against relevant works (LSD-SLAM, SVO, etc.)
- Open-source

    TODO Add here

### Main features

<!-- .slide: class="center" -->
# Q&A, Discussion
