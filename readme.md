This repository contains the code that was used for the paper "Towards computing low-makespan solutions for multi-arm multi-task planning problems".
A writeup of the content can be found [here](https://vhartmann.com/low-makespan-tamp/), and the paper itself is [here](https://arxiv.org/abs/2305.17527).
It is under active development, the version that was used to produce the result in the paper is tagged.

# Installation
The code depends on [rai](https://github.com/vhartman/rai) and [rai-robotModels](https://github.com/MarcToussaint/rai-robotModels).
The path to rai needs to be added in the Makefile, and rai-robotModels should be in the same parent forlder as this project.

Compilation then works with 
```
make -j8
```

In case of issues, try

```
make cleanAll
```

To update dependencies

```
make depend
```

Also have a look at the intructions in 'rai'.

# Usage
Flags:
- mode [test/show\_plan/random\_search/greedy\_random\_search/simulated\_annealing]
- pnp [true/false]
- stippling\_pts [lots]
- env [lab/'']

# To Do
#### Misc
- Ensure correct dependencies of rai/rai-robotModels: possibly make a submodule
- Tests
- Performance benchmark to ensure changes improve things
- Optimization benchmark to compare different search approaches

#### Code
- split main planning subroutine
- fix loading and visualization of previously computed paths
- get rid of warnings

#### Speed improvements
- squeaky wheel planner
- simulated annealing
- speed up komo runs
- more sensible search approach: use the fact that we can cache the end

#### Capabilities
- enable things that are not only 'go to point', e.g. drawing a line
- Take multiple poses into account for 'go to point' tasks
- enable search over sequences with precendence constraints
- time-rescale path
- enable multi-arm cooperation
- look into more complex motion planning:
  - joint optimization
  - constrained sampling based planning
  - inspired by the CMA-ES method?
- more statistics
- joint optimization over the whole path
- reuse more computations (e.g., dummy paths)
- better (closed form?) approximation of lower bound

#### Execution
- Replanning?
- Controller synthesis
- Optimizing for robustness

# Citation
If you use this codebase in your research, please cite the paper where the codebase is from as

```
@misc{23-hartmann-ICAPSws-robplan,
  title = {Towards computing low-makespan solutions for multi-arm
  		  multi-task planning problems},
  author = {Hartmann, Valentin N. and Toussaint, Marc},
  year = {2023},
  howpublished = {ICAPS Workshop on Planning and Robotics},
  arxiv_pdf = {2305.17527}
}
```
