**Reynolds's boids with GPGPU in TurtleKit**
-------------
#### Application of GPU Environmental Delegation of Agent Perceptions

> **Note:** http://dx.doi.org/10.1007/978-3-319-31447-1_5

----------

### The Obtained Flocking Dynamics
You will find in this repository 5 videos of our simulations. In these videos, the agents have a different color according to their behavior : separate (red), align (blue) and cohesion (green). When the concentration of the agents increases, the color turn into white.

| Video name | Hardware | Environment size | Agents population | Field of View |
| --- | ---  | ---  | ---  | --- |
|A4000fov5cpu256 | CPU | 256 x 256 | 4 000  | 5 |
|A4000fov10gpu256 | CPU + GPU | 256 x 256 | 4 000  | 10 |
|A8000fov5gpu512 | CPU + GPU | 256 x 256 | 10 000 | 5 |
|A10000fov5gpu256 | CPU + GPU | 512 x 512 | 8 000 | 5 |
|A10000fov10gpu512 | CPU + GPU | 512 x 512 | 10 000 | 10 |

> **Note:** The 5 videos are in the videos directory

----------

### Reynolds's Boids: Our Model and Implementation

Each entity has a global behavior which consists in moving while adapting its speed and direction. To this end, the proximity with the other agents is tested and the different Reynolds's rules are activated according to the distance found. More exactly, every agent looks in its vicinity. If no agent is present, it continues to move in the same direction. Otherwise, the agent checks if the neighbors are not too close. Depending on the proximity between entities, agents separate (R.1), align with other entities or create cohesion (R.2). Then agents adapt their speed (R.3), move and restart the process.
![Global behavior](https://github.com/ehermellin/Flocking_GPGPU_TurtleKit/raw/master/images/GLobalBehavior.png)
Our test machine is composed of an Intel i7-4770 processor (Haswell generation, 3.40 GHz) and an Nvidia K4000 graphics card (768 CUDA cores). Figure below compares the simulation speed for various population size in an 256 x 256 environment (left) and in an 512 x 512 environment (right). 
![Simulation speed](https://github.com/ehermellin/Flocking_GPGPU_TurtleKit/raw/master/images/Res256.png)
![Simulation speed](https://github.com/ehermellin/Flocking_GPGPU_TurtleKit/raw/master/images/Res512.png)

> **Note:** To test our implementation follow the link : https://github.com/fmichel/TurtleKit

----------

### Boids in Current MABS Platforms

Among the related works found, we only introduce models we were able to download and try! All of the source codes of these examples can be fin in the source directory of this repository.

* NetLogo
* Starlogo
* GAMA
* MasOn
* MadKit
* FlameGPU
* Repast

----------
