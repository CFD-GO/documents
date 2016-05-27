Milestones
==========

## Handler rewrite

Aiming at a complete rewrite of the Handler mechanism

##### What are Handlers:

Handlers are the classes which realize the logic/action described by each XML element in the config. There is a Handler for `<VTK ...>` and for `<Solve ...>`

##### What are the problems now

- The handlers are created and initiated when the xml element is encountered. 
This means that if there is an error in an element at the end of XML file, it will crash the simulation after going for a long time
- All the Handlers are realized in one C++ file `Handlers.cpp`
- The Handlers cannot 'register' or 'broadcast' any behavior prior to being initialized.
This for instance prevents allocating enough memory at the start of the simulation to accomodate some behavior in the future.

##### What should be done:

- Handlers will be registered in a C++ Factory Pattern
- All handlers will be created and initiated when loading the xml file.

##### What would  be nice to do

- It would be nice if the factory registration and attribute check would use the same data that would be used by GUI - a preliminary version is at [doc/elements.yaml](https://github.com/CFD-GO/TCLB/blob/develop/doc/elements.yaml)

## [Chimera support](https://github.com/CFD-GO/TCLB/milestones/Chimera)

Aiming at a full multi-level multi-overlapping-mesh support

##### What Chimera is

Chimera is method of CFD simulation on overlapping meshed. The meshes can be fine and coarse, can move and can intersect in wierd ways.

##### What are the problems now

There is no support for multiple meshes. There is no mesh refinement.

##### What should be done

- Calculation on several meshes (done)
- Load balance between meshes (done)
- Refinement of the time step between meshes
- Interpolation and data transfer between meshes

##### What would be nice to do

- Auto adaptation (creation/movement of mesh wrt. some criterion)

## Discreet Element Method

Aiming at the support for discrete matter simulation support

##### What DEM is

DEM is the tracking and simulation of discrete matter particles immersed in the fluid. It deals both with fluid-structure interaction and contact mechanics etc.

##### What are the problems now

There is no support whatsoever for DEM in TCLB.

##### What should be done

- Introduce structures to keep the particle data
- Calculate the impact of the particles on the fluid in some fast and local way
- Exchange the particle data accross mesh partition between MPI/GPUS

##### What would be nice to do

- Load balance the interparticle calculations between GPUs or CPUs
