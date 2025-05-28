# tlb_generator
A generator of instances for the Target-Level Bike (TLB) problem that simulates a non-homogenous Poisson process. The instances can be solved by the Benders' algorithm in [Technical Report](https://www.cirrelt.ca/documentstravail/cirrelt-2025-02.pdf)

The data is taken from the work of [Datner et al., (2017)](https://pubsonline.informs.org/doi/abs/10.1287/trsc.2017.0790)

## Building the code in Linux

1. Clone the repository and add executable permission to a script that will compile and link for you:

```shell
git clone https://github.com/lucasparada20/tlb_generator.git
cd tlb_generator
chmod u+x build_datner_gen.sh
```
2. Build the code by typing:

```bash
./build_datner_gen.sh
```

if you want to debug or use valgrind, just type:

```bash
./build_datner_gen.sh debug
```

```bash
./build_datner_gen.sh valgrind
```

Since the data is given in Matlab files, the generator uses the (Libmatio)[https://packages.debian.org/source/sid/libmatio] library to parse them. The build script will check if Libmatio is found in your system; otherwise, it can be installed with the following:

```bash
sudo apt install libmatio-dev
'''

## Running the code

Inside the tlb_generator directory, you will find a script run_datner_gen.sh with sample command line calls. The format is:

* trips_rates_file : The path to the file containing the data for incoming and outgoing rates to the stations.
* stations_locations_file : The path to the file containing the capacities of the stations.
* nb_scenarios : The integer number of scenarios in which you want to estimate/train the algorithm.
* nb_test_scenarios : The integer number of scenarios in which you want to evaluate/test the solution.
* seed : The integer to initialize the pseudo-random generator for the Poisson process. As a good practice, set it to a high value, non-negative integer.

Following conventional Sample Average Approximation (SAA) methodologies : nb_Scenarios <<< nb_test_scenarios. In the examples, we set nb_scenarios = 100 and nb_test_scenarios = 400.

In the directory *instances_datner* you will find the instances already built (and compressed).

