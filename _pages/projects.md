---
permalink: /projects/
title: "A collection of research projects I've work on"
classes: wide
date: 2022-08-15T03:02:20+00:00

---
<br/>

## Routing Problems Considering Value System for Exploration Missions (2020-2023)

## Data-Driven Flow Modeling and Analysis (2020-2023)

## Waypoint-Constrained Optimal Control Problem via Interior-point Barrier Method (2021)
A course project for AE551: Introduction to Optimal Control, where I solved an trajectory optimization problem with waypoint constraints using the barrier (interior-point) method. This work was divided into two parts. In part 1, the trajectory optimization problem was formulated into a constrained parameter optimization via Hermite-Simpson direct collocation. In part 2, the parameter optimization problem was solved in two ways - MATLAB's _fmincon_ function and a barrier method coded by myself. The results for both methods were compared at the end. During the development, I tested my code on various benchmark (constrained & unconstrained) problems using the [Himmelblau](https://en.wikipedia.org/wiki/Himmelblau%27s_function) function.  [[Final PPT]](/assets/files/AE551_Final_Presentation_DongHoLee_20204453_vF.pdf) [[code]](https://github.com/leedh0124/AE551_Optimal_Control_Trajectory_Optimization_Direct_Methods)


<figure class="half">
    <img src="/assets/images/AE551_Final_A.jpg">
    <img src="/assets/images/AE551_Final_B.jpg">
    <figcaption></figcaption>
</figure>

## Autonomous Navigation and Mission Management Technology (2017-2020)
A three-year research project carried out during my service at the Aerospace Technology Research Institute (ADD) as a research officer. My team and I worked on various mission planning algorithms for safe operation of UAV under dynamic environments, which can be used for unmanned air transportation and urban air mobility (UAM) services. We considered a number of mission profiles considering relative importance, sequence of visitation, and re-planning scenarios. I wrote a C++ code to solve the MILP formulation of planning problem via the [Gurobi](https://www.gurobi.com/) solver. For re-planning, I wrote a fast and efficient code to run on-board the UAV flight computer. The re-planning code is based on the genetic algorithm. You can read a Korean news coverage of this work [here](https://www.yna.co.kr/view/AKR20210511043600504).

## Modular Drone with Self-Configuration Capability (2016)
Modular drone was the first technical project I worked on. This project was carried out as the Undergraduate Research Participation (URP) program in KAIST. In this work, I developed a modular drone which was composed of smaller, individual modules, which when assembled together, can achieve a coordinated flight. These individual modules are capable of self-configuration that enables user to assemble them in any fashion. Once power is on, these modules communicate with each other, determine their module IDs based on their location, and perform coordinated flight. Hardware of individual module and bridge which connects each modules are constructed out of a 3D printer. [[URP Poster]](/assets/files/URP_POSTER_MODULAR_DRONE2016.pdf) [[GIF]](/assets/images/URP_Modular_Drone_Flight_Test_AdobeExpress.gif)

![Module Image]({{ "/assets/images/URP_Single_Module.jpg" | relative_url }}){: .full}
