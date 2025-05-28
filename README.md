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

## Running the code

Inside the tlb_generator directory, you will find a script run_datner_genheur.sh with sample command line calls. The format is:

* trips rates file : Containing the data for incoming and outgoing rates to the stations


