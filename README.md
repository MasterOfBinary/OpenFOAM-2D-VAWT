# OpenFOAM 2D VAWT Simulation
This is a complete OpenFOAM case for simulating the flow through a rotating high solidity vertical axis wind turbine.

It was modified by Vaughn Friesen as a demonstration of [FOAMkit](https://github.com/MasterOfBinary/foamkit).

## Running

To run the case, download FOAMkit and follow its instructions for sourcing the `foamkitenv.sh` file. Then, from the `OpenFOAM-2D-VAWT` directory, run `foamkit`. Perform steps 1-4 (setup), 10 (pre-processing) and 20-21 (running simulation). To monitor the status, start a new instance of `foamkit` (don't ctrl-C the one that's running the simulation! run it in screen or something) and run step 22 (monitor).

## Notes

The solution was computed using `pimpleDyMFoam`. The computational domain consists of a rotating inner zone and a stationary outer zone. 

![ScriptImage](https://raw.github.com/traviscarrigan/OpenFOAM-2D-VAWT/master/grid.png)

This is a 2D moving mesh calculation performed using OpenFOAM's `pimpleDyMFoam` solver. The blade cross section is the NACA 0015 with a rotor solidity of 1.5 and operating at a tip speed ratio of 1.0. You can adjust the tip speed ratio by changing the x-velocity component and the solid body rotation of the rotating cell zone found in the `dynamicMeshDict`. 

A video of the flow field can be found on [YouTube](http://youtu.be/6o4LoV-JINY). 

The mesh was generated using [Pointwise](http://www.pointwise.com/) and can be found in the `constant/polyMesh` directory. Both the exported grid and the Pointwise project files are available. If you have Pointwise, you can open the `vawt-of.pw` file and manipulate and/or regenerate the mesh. You can also use the [VAWTMesh](https://github.com/traviscarrigan/VAWTMesh) script to automatically generate the grid. 
