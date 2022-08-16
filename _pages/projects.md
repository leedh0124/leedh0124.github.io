---
permalink: /projects/
title: "A collection of research projects I've worked on"
classes: wide
date: 2022-08-15T03:02:20+00:00

---
<br/>

## Routing Problems Considering Value System for Exploration Missions (2020-2023)
This is an on-going three-year research project funded by National Research Foundation (NRF) of Korea. Led by Professor Jaemyung Ahn, our team considers the value system inherent in exploration missions and finds an optimal set of routes to accomplish mission goals. Planetory exploration missions such as field geology tests and atmospheric observations for autonomous mobile robots naturally entail various intrinsic traits. Uncertainty is one major factor. As a result, it is often the case to update the current mission profile, a situation that calls for fast and efficient mission re-planning techniques. In this work, I worked on a mission re-planning method for multiple robots using deep reinforcement learning. I designed a Transformer-style policy network and proposed a data-efficient training algorithm using instance-augmentation baseline that speeds up per-epoch training time by over 30% when compared to the conventional method. 
[[Code]](https://github.com/leedh0124/Deep-Dynamic-Transformer-Model-for-Multi-Start-Team-Orienteering-Problem)   

### Related Publications:
- **Dong Ho Lee** and Jaemyung Ahn. (2022). Multi-Start Team Orienteering Problem for UAS Mission Re-Planning with Data-Efficient Deep Reinforcement Learning. _Journal of Intelligent & Robotic Systems_ (under review)
- **Dong Ho Lee** and Jaemyung Ahn. A Deep Reinforcement Learning Approach to solve the Vehicle Routing Problem with Resource Constraints. In _AIAA Scitech Forum 2023_, Maryland, USA. (to appear)

<figure class="half">
    <img src="/assets/images/DH-Research2.jpg">
    <img src="/assets/images/DDTM_Training_cropped.jpg">
    <figcaption></figcaption>
</figure>

![DDTM Training Image]({{ "/assets/images/DDTM_Result_A_cropped.jpg" | relative_url }}){: .align-center}

## Data-Driven Flow Modeling Research (2020-2023)
An on-going three-year research project funded by ADD, jointly conducted with the Aerospace Propulsion Laboratory (APL) of Seoul National University (SNU). Under extreme flow conditions, say Mach number beyond 5.0, changes in aerodynamic design shape frequently occurs. As a result, we need a fast and accurate technique to predict the changes in aerodynamic coefficients in accordance with the shape changes. Along with the team led by Professor Jaemyung Ahn and Professor Bok Jik Lee, I worked on adaptive aerodynamics prediction upon changes of the shape using deep learning. Specifically, I designed a deep learning pipeline for preprocessing raw data and training a residual deep neural net to fine tune its inference performance. 

### Related Publications:
- **Dong Ho Lee**, DongUk Lee, Seoum Han, Lee, Bok Jik Lee and Jaemyung Ahn. (2022). A Residual Deep Neural Network for Prediction of Aerodyanmic Coefficients of Ablated Cone Shape under Extreme Flow Conditions. (preparation)
- **Dong Ho Lee**, DongUk Lee, Jeongyong Lee, Bok Jik Lee and Jaemyung Ahn. Prediction of Multiple Aerodynamic Coefficients of Missiles using CNN. In _AIAA Scitech Forum 2022_, San Diego, USA. 

<figure class="half">
    <img src="/assets/images/AIAA_DongHo_Presentation.jpg">
    <img src="/assets/images/Test Set Plot for Ca.gif">
    <figcaption></figcaption>
</figure>

## Waypoint-Constrained Optimal Control Problem via Interior-point Barrier Method (2021)
A course project for AE551: Introduction to Optimal Control at KAIST, where I solved an trajectory optimization problem with waypoint constraints using the barrier (interior-point) method. This work was divided into two parts. In part 1, the trajectory optimization problem was formulated into a constrained parameter optimization via Hermite-Simpson direct collocation. In part 2, the parameter optimization problem was solved in two ways - MATLAB's _fmincon_ function and a barrier method coded by myself. The results for both methods were compared at the end. During the development, I tested my code on various benchmark (constrained & unconstrained) problems using the [Himmelblau](https://en.wikipedia.org/wiki/Himmelblau%27s_function) function.  
[[Code]](https://github.com/leedh0124/AE551_Optimal_Control_Trajectory_Optimization_Direct_Methods)
[[Final PPT]](/assets/files/AE551_Final_Presentation_DongHoLee_20204453_vF.pdf) 

<figure class="half">
    <img src="/assets/images/AE551_Test_Benchmark_B.jpg">
    <img src="/assets/images/AE551_Final_B.jpg">
    <figcaption></figcaption>
</figure>

## Autonomous Navigation and Mission Management Technology (2017-2020)
A three-year research project carried out during my service at the Aerospace Technology Research Institute (under ADD) as a research officer. My team and I worked on various mission planning algorithms for safe operation of UAV under dynamic environments, which can be used for unmanned air transportation and urban air mobility (UAM) services. We considered a number of mission profiles considering relative importance, sequence of visitation, and re-planning scenarios. I wrote a C++ code to solve the MILP formulation of planning problem via the [Gurobi](https://www.gurobi.com/) solver. For re-planning, I wrote a fast and efficient code to run on-board the UAV flight computer. The re-planning code is based on the genetic algorithm. You can read a Korean news coverage of this work [here](https://www.yna.co.kr/view/AKR20210511043600504).

### Related Publications:
- **Dong Ho Lee**, Hwanchol Jang, Sang-Hwan Kim and Woohyuk Chang. (2020). Multi-UAV Mission Allocation and Optimization Technique Based on Discrete-Event Modeling and Simulation. _Journal of the Korean Society for Aeronautical& Space Systems_, 48(2), 159-166
-  **Dong Ho Lee**, Woohyuk Chang and Jinku Buyn. An Optimization Technique for Discrete Event Model-based UAV Real-Time Heterogeneous Mission Allocation. In 2018 _Proceedings of the Korean Society for Aeronautical and Space Sciences, Fall Conference_, Jeju, Korea.
-  **Dong Ho Lee**, Woohyuk Chang and Jinku Buyn. Discrete-event Modeling and Simulation of Autonomous Multi-UAV Mission Management. In 2018 _Avionics Systems Symposium Korea (ASSK)_, Yeosu, Korea.

## Modular Drone with Self-Configuration Capability (2016)
Modular drone was the first technical project I worked on. This project was carried out as the Undergraduate Research Participation (URP) program in KAIST. In this work, I developed a modular drone which was composed of smaller, individual modules, which when assembled together, can achieve a coordinated flight. These individual modules are capable of self-configuration that enables user to assemble them in any fashion. Once power is on, these modules communicate with each other, determine their module IDs based on their location, and perform coordinated flight. Hardware of individual module and bridge which connects each modules are constructed out of a 3D printer. 
[[GIF]](/assets/images/URP_Modular_Drone_Flight_Test_AdobeExpress.gif)
[[URP Poster]](/assets/files/URP_POSTER_MODULAR_DRONE2016.pdf) 

![Module Image]({{ "/assets/images/URP_Single_Module.jpg" | relative_url }}){: .align-center}
