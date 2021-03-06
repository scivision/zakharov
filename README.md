# Langmuir-1D Simulation

[![image](https://zenodo.org/badge/DOI/10.5281/zenodo.168586.svg)](https://doi.org/10.5281/zenodo.168586)
![ci_cmake](https://github.com/space-physics/zakharov/workflows/ci/badge.svg)

Zakharov Simulation

Originally authored by Hassanali Akbari as part of his PhD work.

Michael Hirsch converted to Fortran 2008, and works with `gfortran`, `ifort`, `flang` and other Fortran compilers on any operating system and computer.

The procedure to use this program is as follows:

1.  Build the Fortran code
2.  run the simulation
3.  plot with Matlab

## Build

* Linux

    ```sh
    apt install g++ cmake libboost-filesystem-dev libboost-program-options-dev
    ```
* Mac

    ```sh
    brew install gcc boost
    ```

and then

```sh
cmake -B build

cmake --build build --parallel
```

## Run Simulation

arguments are: output_directory simulation_end_time electron_beam_env(as many beams as you like):

```sh
./zakhfort /tmp/test 1e-4 300
```

### C++

```sh
./zakh --ev 300 -o /tmp/testcxx
```

* `--ev` beam energy
* `-o` output directory (will be created if it doesn't exist)

### Plot Results

From GNU Octave or Matlab:
```sh
Sim_v6_3_Linux(0, /tmp/test)
```
