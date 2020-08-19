The ETMC has performed three pion scattering on `N_f = 2` Wilson clover twisted mass lattices. In this repository you can find the energy levels such that an independent analysis is possible. If you are using this data in a publication, we ask you to cite !(arXiv:2008.03035)[https://arxiv.org/abs/2008.03035].

There is the spectrum in the files starting with `cm_mass`. These contain the interacting center of mass energies, the pion mass and their ratio. The files with `pion_decay` contain the pion decay constant that is measured on the same data with full correlation.

Files with `boot` in their name contain all bootstrap and jackknife samples, the other files contain the central values and an error estimate from the samples. Unfortunately both resampling methods are called “boot” in this data set, so “boot” should rather mean “samples”. Jackknife and bootstrap data is given in separate files.

The data files are space separated, you can read them in R with `read.table` and in Python with `np.loadtxt` or `np.genfromtxt`. The following table explains all the columns. It is recommended to use a library that can group data, either Python Pandas or R dplyr.

| Column | Type | Meaning |
| --- | --- | --- |
| `ensemble` | String | Name of the ETMC ensemble. |
| `extent_space` | Integer | Number of lattice sites in the spatial direction, `L/a`. |
| `extent_time` | Integer | Number of lattice sites in the temporal direction, `T/a`. |
| `channel` | String | Scattering channel, either `2pi_I2` or `3pi_I3`. |
| `irrep` | String | Name of the irrep, like `A1u` or `Eg` or `B2.` |
| `total_momentum_d_sq` | Integer | Total momentum squared. |
| `irrep_col` | Integer | Column of the irrep. We only use 1. |
| `irrep_row` | Integer | Row of the irrep, we only use 1. |
| `outlier_cutoff` | Float | Gauge configurations which yield a correlator value `C_{ij}(t)` which is more than `outlier_cutoff` inter quartile ranges away from the quartiles is considered an outlier and discarded. |
| `boot_method` | String | Resampling method, either `bootstrap` or `jackknife`. |
| `boot_R` | Integer | Number of bootstrap samples. Meaningless for jackknife resampling. |
| `boot_seed` | Integer | Seed used in bootstrap resampling. |
| `boot_l` | Integer | Bootstrap block length. |
| `pion_total_momentum_d_sq` | Integer | The total momentum squared of the pion correlator used. |
| `pion_tmin` | Integer | Begin of the pion correlator fit range. |
| `pion_tmax` | Integer | End of the pion correlator fit range. |
| `gevp_sort_type` | String | Sorting algorithm in the GEVP, can either be `values` or `vectors`. |
| `gevp_mask` | Integer/NA | If set to `NA`, the whole correlator matrix is fed into the GEVM. Integer values mean that only the lowest so many operators have been considered. |
| `correlator_id` | Integer | Number of the correlator in that irrep, increasing number means increasing energy |
| `fit_method_count` | Integer | Number of fit methods that have been averaged on this energy level. |
| `boot_r` | Integer | ID of the sample, only present in the files with the resampling. |
| `cm_mass_val` | Float | Center of mass energy value in lattice units. |
| `cm_mass_boot` | Float | … on the sample `boot_r`. |
| `cm_mass_err` | Float | … error. |
| `pion_mass_val` | Float | Pion mass value in lattice units. |
| `pion_mass_boot` | Float | … on the sample `boot_r. |
| `pion_mass_err` | Float | … error. |
| `cm_mass_over_pion_mass_val` | Float | Ratio center of mass energy over pion mass, value. |
| `cm_mass_over_pion_mass_boot` | Float | … on the sample `boot_r. |
| `cm_mass_over_pion_mass_err` | Float | … error. 
| `pion_decay_constant_val` | Float | Pion decay constant in 120 MeV convention. |
| `pion_decay_constant_boot` | Float | … on the sample `boot_r. |
| `pion_decay_constant_err` | Float | … error. 

