# CMP-project3
## N-body simulation of galaxy merger
This is the public repository for the code of N-body simulation of galaxy merger. This code can set initial positions and velocities of galaxy(contained disk and bulge) following a Kuzmin's disk potential and a Hernquist's bulge potential. The acceleration for each time step is calculated by using octree method and using leap frog algorithm to update the position and velocity for each particles. This can be use to analyse the following properties of one **single galaxy**:
- 2D animation of one self-evolved single galaxy
- Energy plot of the system

<br/>And it can also be used to simulate the **merger of two galaxies** and analyse the following properties:
- 2D animation of two galaxies merger
- Energy plot of the system
- Separation plot of the center of mass

<br/>We also provide you a specific case, to simulate the **merger of Milky Way and Andromeda**.

### Installation
Now this code can be worked on **Windows** system. Before installation, make sure your system meets the prerequisites listed in **Dependencies**, list below.
<br/>To install, there are two ways:
1. **Download this repository**
<br/>You can go to our [github page](https://github.com/boson112358/cmp-project) to download it and save it on your machine
2. **Clone this repository**
<br/>Clone it on your machine:
```
git clone https://github.com/boson112358/cmp-project
```
#### Dependencies
The code requires the following(some of the functionality might work with older versions):
- Python version 3.9+
- argparse >= 1.4.0
- matplotlib >= 3.3.4
- numpy >= 1.20.1
- tqdm >= 4.59.0
### Running
#### 1. Simulating one single galaxy
First, we can use this code to generate one single galaxy contained disk and bulge. By running `testSingleGalaxy.py`, it can generate the animation of given timestep, the plot of number of force calculation, the initial position distribution of galaxy in xy plane and the particle's trajectory plot. You can find the plot in the folder `./plot`. In our repository, we provide you a bat profile `runSingleGalaxy.bat` with some arguments. You can change the corresponding arguments to get the self-evolved single galaxy you want. For this simulation, you can use the following arguments: ParticleNumber, Step, Length, MultipleMass, EnergyTracking. For the initial condition quantities you set, you can find it in the folder `./data`, named `output.txt`.

```
python testSingleGalaxy.py --ParticleNumber 200 --Step 200 --MultipleMass 2
```
#### 2. Simulating two galaxies merger
Second, we can use this code to simulate merger of two galaxies. By running `testMergerTwoGalaxy.py`, it can generate the animation of given timestep, the plot of number of force calculation, the initial position distribution of galaxies in xy plane, the particle's trajectory plot and the separation distance of center of mass plot. You can find the plot in the folder `./plot`. In our repository, we provide you a bat profile `runMergerTwoGalaxy.bat` with some arguments. You can change the corresponding arguments to get the merger senario you want. For this simulation, you can use the following arguments: ParticleNumber, Step, Length, MultipleMass, MassRatio, EnergyTracking. For the initial condition quantities you set, you can find it in the folder `./data`, named `output.txt`.
```
python testMergerTwoGalaxy.py --ParticleNumber 200 --Step 100 --MassRatio 2
```
What's more, now in our code, we only set the two galaxies with a distance of 20 units in x-axis, we encourage you to set the initial postions and velocities in the profile `testMergerTwoGalaxy.py`, to change the following two lines(the last six parameters is (x,y,z,vx,vy,vz)):
```
galaxy1 = make_galaxy(N1d, M1d, N1b, M1b, 0, 0, 0, 0, 0, 0)
galaxy2 = make_galaxy(N2d, M2d, N2b, M2b, 20, 0, 0, 0, 0, 0)
```
#### 3. Simulating the Milky Way and Andromeda merger
Third, we can use this code to simulate merger of Milky Way and Andromeda. We set the initial positions and velocities for Milky Way and Andromeda merger. By running `runMWandM31.py`, it can generate the animation of given timestep, the plot of number of force calculation, the initial position distribution of galaxies in xy plane, the particle's trajectory plot and the separation distance of center of mass plot. You can find the plot in the folder `./plot`. In our repository, we provide you a bat profile `runMWandM31.bat` with some arguments. You can change the corresponding arguments to get the merger senario you want. For this simulation, you can use the following arguments: ParticleNumber, Step, Length, MultipleMass, EnergyTracking. For the initial condition quantities you set, you can find it in the folder `./data`, named `output.txt`.
```
python testMWandM31.py --ParticleNumber 200 --Step 200 --Length 200 --MultipleMass 4
```

The following is the explaination of argument. 
1. --Temperature
<br/>Set the initial temperature of system. The default value is 1.
2. --Lattice
<br/>Set the width of the grid in spin sites. The default value is 50.
3. --Equilibrium_time
<br/>Set the time duration until system considered in equilibrium. The default value is 1000.
4. --Correlation_time
<br/>Set the system correlation time. The default value is 1.
5. --Total_Duration
<br/>Set the time duration the total simulation will run in correlation mode. The default value is 3000.
6. --Data_Points
<br/>The amount of independent blocks to calculate thermal properties. The default value is 20.
7. --Correlation_Mode
<br/>Turn on the correlation mode.
8. --Thermodynamic_Mode
<br/>Turn on the thermodynamic mode. 
9. --No_Plot
<br/>Allows plots to be turned off. Otherwise, when using these two modes, you can find the corresponding plots in folder `./plot`.
### Relevant material
For more detail about our code, you can check out our presentaion slides in this repository.
### Authors
- [Davey Plugers](https://github.com/DaveyPlugers)
- [Zhen Xiang](https://github.com/boson112358)
