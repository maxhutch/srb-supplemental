srb-supplemental
================

Supplemental information for "The Shirley reduced basis: a reduced order model for plane-wave DFT"

Each directory is setup as a test suite for use will the qe-test.py script (see maxhutch/qe-tools).
This includes a pseudo directory with pseudopotentials and a config file
If you want to use the script's comparison abilities, you'll need to run the ref job once and put
the output back into the ref directory.

## CNT, Au, and Ni
 * ref: reference plane-wave calculation
 * srb: srb calculation with defaults
 * srb-opt: srb calculation that satisfies agreement constraints
 * fast: srb calculation that satisfies relaxed agreement constraints (e.g. forces only for MD)
 * no-red: no reduced density matrix
 * no-aux : no auxiliary projectors

## Au
 * q-cor : only use BZ corners for q-points
 * q-edg : use BZ corners and edge centers for q-points
 * q-cen : use BZ corners, edge centers, face centers, and zone center for q-points
 * red{N} : defaults + \sigma_x^2 = 1.d-{N} (except for N=0, which is \sigma_x^2 = 0)
 * tol{N} : defaults + \sigma_b^2 = 1.d-{N} (except for N=0, which is \sigma_b^2 = 0)

## CNT
 * dens{N} : defaults + \sigma_\rho^2 = 1.d-{N} (except for N=0, which is \sigma_\rho^2 = 0)

## Ni
 * fre-{N} : defaults + \epsilon_f = 1.d-{N} (except for N=0, which is \epsilon_f = 0)
 * sav-{N} : defaults + n_L = {N}

## Au-conv
These directories contain sweeps of E_cut.  The runs srb-{N} and ref-{N} have Ecut = {N}.
The ref job has E_cut = 128.
The suffix of the directory, i.e. Au-conv-{D}, is the negative log of \sigma_b^2.
That is, Au-conv-{D} has srb runs with \sigma_b^2 = 1.d-{D}.
The directory with no suffix has D = 14, which is a good approximation of zero in this
context.

