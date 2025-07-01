# Real_Munc-Real_NMDAR_syn19

Use MCell3 to run the simulations.
https://mcell.org/

1. real munc positions and real NMDAR positions of syn #19 is in Real_Munc-Real_NMDAR.
For other synapses (a) replace the synapse border from border_other_synapses (and rename it to Scene.geometry_border.mdl)
(b) use the synapse munc and NMDAR positions and ids and put them in files:
Scene.reactions.mdl and munc_release_site.mdl.

In file Scene.reactions.mdl use the desired reaction rates (here a file called "release2.txt")  to activate the reaction. if it is [0] it means that the reaction is not included in the simulation. In the example below, only  munc_1 -> munc_1 + Glu is active.

...
DEFINE_REACTIONS {

munc_1, -> munc_1, + Glu, ["release2.txt"]
munc_2, -> munc_2, + Glu, [0] 
munc_3, -> munc_3, + Glu, [0] 
munc_4, -> munc_4, + Glu, [0] 
...

The same for the receptor reaction with Glu.

====

2. Grid Munc simulation code (for syn 17) is in source_code_syn17_MuncGrid
Use the grid position from grid.mdl and run your mcell simulations for each grid site.
put the position in file munc_release_site.mdl in:

/* munc grid */ 
munc_g1,[ 0.000, 0.000, 0.0075]

For other synapsesfollow the above instructions.

====

3. Grid NMDAR simulation code (for syn 17) is in source_code_syn17_NMDAR_Grid.
GluN2A is in 2A folder and GluN2B is in 2B.

Again, use the grid positions from Agrid3 and Bgrid3 files.
put the grid position you want to simulate in the munc_release_site.mdl in:

/* NMDAR grid */ 
GluN2A_g1,[ 0.000, 0.000, -0.0075]


