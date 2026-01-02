# Mobile-wheeled-robots-and-visual-servoing

 <a href= "https://img.shields.io/badge/github-repo-blue?logo=github"> <img src="https://img.shields.io/badge/github-repo-blue?logo=github" alt="GitHub Badge"/></a>
<a href= "https://img.shields.io/badge/CoppeliaSim-v4.10-orange"> <img src="https://img.shields.io/badge/CoppeliaSim-v4.10-orange" alt="Coppelia Badge"/></a>
<a href= "https://img.shields.io/badge/Lua--blue"> <img src="https://img.shields.io/badge/Lua--blue" alt="Lua Badge"/></a>
<a href= "https://img.shields.io/badge/License-Apache--2.0-yellow"> <img src="https://img.shields.io/badge/License-Apache--2.0-yellow" alt="License Badge"/></a>


Lab assignments that apply simple concepts related to mobile robots and visual servoing on CoppeliaSim with codes written in Lua.
The lab subject is divided into 4 parts :

1. **Control of an omnidirectional robot** (Commande d'un robot omnidirectionnel)
2. **Control of a differential drive robot**  (Commande d'un robot à entraînement differentiel) 
   - 2.1 Tracking a Cartesian trajectory  (Suivi d'une trajectoire cartésienne)
   - 2.2 Position control (Régulation de position)
3. **Potential fields for trajectory planning** (Champs de potentiel pour la planification de trajectoire)
4. **Image-based visual servo control (IBVS)** (Asservissement visuel basée sur les images) - **to do**

# Results

1. **Control of an omnidirectional robot**
<div align="center">
<img alt="Illustration" src="1_Control of an omnidirectional robot/omnidirectionalControl_start.gif" width="50%" height="50%"> </img>
</div>

2. **Control of a differential drive robot**
   - 2.1 Tracking a Cartesian trajectory
<div align="center">
<img alt="Illustration" src="2_Control of a differential drive robot/monocycle_suiviTrajectoire_start.gif" width="50%" height="50%"> </img>
</div>

   - 2.2 Position control
<div align="center">
<img alt="Illustration" src="2_Control of a differential drive robot/monocycle_waypoints_start.gif" width="50%" height="50%"> </img>
</div>

3. **Potential fields for trajectory planning**
<div align="center">
<img alt="Illustration" src="3_Potential fields for trajectory planning/3_potentials_start_update_2026.gif" width="50%" height="50%"> </img>
</div>

Explanations:

At each iteration of the algorithm, we take stock of some artifical attractive forces (final reference point) and repulsive forces (obstacles such as walls) acting on the robot. 
We calculate the direction of the resulting artificial force and multiply it by an amplitude equal to the distance to be traveled in one time step (distance = speed × time step).
This gives us an intermediate point at each iteration, and we use the controller from the previous parts to guide the robot to each intermediate point and finally to the final attractive point.
The parameters of the attractive and repulsive forces must be carefully chosen, otherwise the robot may not reach the attractive point, the end point, and remain stuck in a local minimum potential between two obstacles.

<!-- To better understand the robot's intermediate movements and help adjust the configurable force parameters, a Goal indicator has been added, which corresponds to the intermediate point to be reached. -->





# Credits
These lab assignments were given for the course Robotics (Robotique ELE8203), at the engineer school Polytechnique Montréal (Québec, Canada), in 2021.
