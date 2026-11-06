---
permalink: /projects/
title: "Research"
excerpt: "Games of ordered preference, compact reformulations, and a Newton solver for real-time multi-agent planning and control."
classes: wide
---

I study how agents plan and act when their objectives conflict and some goals take priority over others. My work combines **noncooperative game theory, numerical optimization, and optimal control**, with applications to multi-agent systems.

## Current work: receding-horizon control with ordered objectives
{: #current-work}

I develop efficient numerical methods to solve **Games of Ordered Preference (GOOP)** for real-time receding-horizon control. The examples below show **preliminary results**.

### Highway overtaking

<div class="research-project-row research-project-row--wide" markdown="1">

<figure class="research-figure">
  <a href="{{ '/assets/images/research/overtake.pdf' | relative_url }}" aria-label="Open the highway overtaking figure as a PDF">
    <img src="{{ '/assets/images/research/overtake.png' | relative_url }}" alt="The red ego vehicle changes lanes to overtake a blue vehicle, with a plot checking inter-vehicle proximity along the planned trajectories." width="1300" height="550" loading="lazy">
  </a>
  <figcaption>Planned trajectories and collision-avoidance check.</figcaption>
</figure>

<div class="research-project-text" markdown="1">

The ego vehicle (red) overtakes the blue vehicle while anticipating its behavior through a game-theoretic model. The compact reformulation and Newton solver reduce the computational burden, enabling real-time trajectory computation with longer planning horizons in this preliminary example.

</div>
</div>

### Cooperative pot transfer

<div class="research-project-row research-project-row--wide" markdown="1">

<figure class="research-figure">
  <a href="{{ '/assets/images/research/goop_tilt_swerve_annotated.gif' | relative_url }}" aria-label="Open the cooperative pot-transfer animation">
    <img src="{{ '/assets/images/research/goop_tilt_swerve_annotated.gif' | relative_url }}" alt="Two robot arms transfer a pot while keeping it balanced and maintaining clearance from an adversarial robot's hand, shown from two viewpoints." width="800" height="300" loading="lazy">
  </a>
  <figcaption>Two views of the manipulation simulation.</figcaption>
</figure>

<div class="research-project-text" markdown="1">

In this simulation, two robot arms cooperate to transfer a pot while keeping it balanced and maintaining clearance from an adversarial robot's hand. The adversary tries to obstruct the transfer, so the cooperating arms must anticipate and respond to its motion.

</div>
</div>

## Games of Ordered Preference
{: #ordered-preferences}


### The problem

<div class="research-project-row" markdown="1">

<figure class="research-figure">
  <a href="{{ '/assets/images/research/GOOP_illustration.pdf' | relative_url }}" aria-label="Open the ordered-objectives illustration as a PDF">
    <img src="{{ '/assets/images/research/GOOP_illustration.png' | relative_url }}" alt="An example hierarchy of driving objectives: collision avoidance has highest priority, followed by respecting lane boundaries, obeying speed limits, and reaching the destination efficiently." width="1350" height="1083" loading="lazy">
  </a>
  <figcaption>An example of ordered driving objectives.</figcaption>
</figure>

<div class="research-project-text" markdown="1">

A robot may need to prioritize collision avoidance over progress, or task completion over energy efficiency. In a multi-agent setting, the outcome also depends on what other robots do. The question is how to compute decisions that respect each agent’s objective hierarchy while accounting for strategic interaction.

</div>
</div>

### The solution

<div class="research-project-row" markdown="1">

<figure class="research-figure">
  <a href="{{ '/assets/images/research/GOOP_Formulation.pdf' | relative_url }}" aria-label="Open the GOOP formulation figure as a PDF">
    <img src="{{ '/assets/images/research/GOOP_Formulation.png' | relative_url }}" alt="Coupled objective hierarchies for two players, followed by a KKT reformulation of the nested optimization problem." width="1060" height="813" loading="lazy">
  </a>
  <figcaption>GOOP formulation and single-level reformulation.</figcaption>
</figure>

<div class="research-project-text" markdown="1">

We developed **Games of Ordered Preference (GOOP)**, a mathematical framework that models noncooperative games with strictly ordered preferences. We derived optimality conditions and solved a sequence of relaxed mixed complementarity problems to compute equilibrium candidates.

The original formulation can require exponentially many variables and constraints. In follow-on work, our team derived a **reduced KKT system whose size grows polynomially**, eliminating unnecessary variables and constraints. For quadratic objectives with linear constraints, the reduced and complete systems have the same primal solution sets; in general nonlinear problems, additional conditions are needed to certify equilibrium candidates.

The reported benchmark showed up to 10× speedup from the **formulation change alone**. The ongoing work above builds on the reformulation with a Newton solver for real-time receding-horizon control.

</div>
</div>

### Relevance to robotics

<div class="research-project-row" markdown="1">

<figure class="research-figure">
  <a href="{{ '/assets/images/research/GOOP_Intersection.pdf' | relative_url }}" aria-label="Open the GOOP intersection figure as a PDF">
    <img src="{{ '/assets/images/research/GOOP_Intersection.png' | relative_url }}" alt="Two vehicles with different objective priorities at an intersection: blue prioritizes reaching its goal and red prioritizes the speed limit." width="750" height="815" loading="lazy">
  </a>
  <figcaption>Different objective priorities at an intersection.</figcaption>
</figure>

<div class="research-project-text" markdown="1">

GOOP lets each agent express which objectives take priority when planning around others. The intersection example illustrates how different priorities can lead to different driving behavior.
- [Paper](https://doi.org/10.1109/LRA.2025.3575324) · [Code](https://github.com/CLeARoboticsLab/ordered-preferences)
- [Preprint](https://arxiv.org/abs/2603.26950) · [Code](https://github.com/CLeARoboticsLab/Reduced-GOOP) — under review at *SIAM Journal on Optimization*.
- Related collaborative work: [Approximate Solutions to Games of Ordered Preference](https://arxiv.org/abs/2507.11021), ITSC 2025.

</div>
</div>

## Mixed-hierarchy games for robot interaction
{: #mixed-hierarchy}

Multi-robot systems can mix simultaneous decisions with leader–follower relationships. I co-developed methods for **mixed Nash/Stackelberg games**, using quasi-policy approximations to make their optimality conditions computationally manageable.

The team evaluated the solver in simulation and in a receding-horizon experiment with **two Clearpath Jackals and an NVIDIA JetRacer**.
[Paper](https://arxiv.org/abs/2602.01568) · [Code](https://github.com/CLeARoboticsLab/MixedHierarchyGames.jl)

## Game-theoretic hierarchical routing
{: #hierarchical-routing}

<div class="research-project-row" markdown="1">

<figure class="research-figure">
  <a href="{{ '/assets/images/research/hierarchical_routing.pdf' | relative_url }}" aria-label="Open the hierarchical routing figure as a PDF">
    <img src="{{ '/assets/images/research/hierarchical_routing.png' | relative_url }}" alt="A high-level router assigns routes while individual vehicles solve their trajectory-planning problems." width="1275" height="515" loading="lazy">
  </a>
  <figcaption>High-level route assignment and low-level trajectory planning.</figcaption>
</figure>

<div class="research-project-text" markdown="1">

A high-level planner assigns routes, while individual vehicles optimize their own behavior along those routes. I developed a **convex reformulation and a customized branch-and-bound method** for this bilevel routing problem. The method finds a globally optimal solution for the modeled problem while accounting for strategic interactions among vehicles.
[Paper](https://doi.org/10.1109/LCSYS.2025.3571655)

</div>
</div>

## Learning to replan multi-UAV routes
{: #learning-routing}

When a mission changes, vehicles may be far from the depot and have different remaining fuel or time budgets. I built a **Transformer-based reinforcement learning policy** for this multi-start team orienteering problem and developed a data-efficient training method.

The policy selects routes under resource constraints, and the training approach was also evaluated on traveling salesperson and capacitated vehicle routing problems.
[Paper](https://doi.org/10.1007/s10489-024-05367-4) · [Paper](https://doi.org/10.2514/6.2023-2662) · [Code](https://github.com/leedh0124/Deep-Dynamic-Transformer-Model-for-Multi-Start-Team-Orienteering-Problem)

<figure class="research-figure">
  <img src="{{ '/assets/images/DDTM_Result_A_cropped.jpg' | relative_url }}" alt="Multi-UAV routing results from the learning-based replanning project" loading="lazy">
  <figcaption>Route-planning results from my KAIST work on data-efficient deep reinforcement learning.</figcaption>
</figure>

## Information gathering in noncooperative games

How should an agent allocate resources to learn about another agent’s objectives before interacting with it? I contributed to a two-stage game-theoretic framework and a gradient-based solution method for smooth information gathering.
[Paper](https://www.ifaamas.org/Proceedings/aamas2025/pdfs/p1595.pdf) · [Code](https://github.com/CLeARoboticsLab/GamesVoI.jl)

## Earlier research and engineering
{: #earlier-work}

### Deep learning for aerodynamic prediction

At KAIST, I developed a residual neural-network pipeline to predict **changes in aerodynamic coefficients as a vehicle’s shape changes under extreme flow conditions**. The work involved preprocessing simulation data, training the model, and evaluating prediction performance.
[Paper](https://doi.org/10.1016/j.ast.2023.108207) · [Paper](https://doi.org/10.2514/6.2022-2439)

### Trajectory optimization with waypoint constraints

For a KAIST optimal-control course project (2021), I formulated a waypoint-constrained trajectory problem using **Hermite–Simpson direct collocation**. I implemented an interior-point barrier method and compared its results with MATLAB’s `fmincon`.
[Code](https://github.com/leedh0124/AE551_Optimal_Control_Trajectory_Optimization_Direct_Methods) · [Project slides (PDF)]({{ '/assets/files/AE551_Final_Presentation_DongHoLee_20204453_vF.pdf' | relative_url }})

### Multi-UAV mission planning

As a Research Officer at ADD (2017–2020), I developed **mixed-integer and genetic-algorithm approaches** for mission allocation and replanning, and implemented planning software for a Linux-based UAV simulator. This work led to a registered patent, **KR102063851** (2020).

### Self-configuring modular drone

As an undergraduate research intern at KAIST (2015–2016), I designed and constructed a **3D-printable modular drone**. The modules communicate to identify their arrangement before coordinated flight. The project received an Excellent Research Award in the Undergraduate Research Participation program.
[Flight demonstration (MP4)]({{ '/assets/images/URP_Modular_Drone_Flight_Test.mp4' | relative_url }}) · [Research poster (PDF)]({{ '/assets/files/URP_POSTER_MODULAR_DRONE2016.pdf' | relative_url }})

<figure class="research-figure research-figure--compact">
  <img src="{{ '/assets/images/URP_Single_Module.jpg' | relative_url }}" alt="A single 3D-printed module from the self-configuring drone project" loading="lazy">
  <figcaption>A module from the self-configuring drone prototype.</figcaption>
</figure>
