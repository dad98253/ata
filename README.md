# ata
Gierhart-Johnson Area Radio Propagation Analysis Program


The ata program was written by Gierhart and Johnson. It is an implemenation of the IF-73
(FAA·RD-73-103) radio wave propagation model. The IF-73 model is useful in estimating
service coverage for radio systems operating in the 0.1 to 20 GHz frequency range.
It is applicable to many air/air, air/ground, air/satellite, ground/ground, and
ground/satellite systems. Irregular terrain and propagation beyond the line-of-sight
range are considered in the model. However, the terrain feature is keyed to the lower
(or facility) antenna and the radio horizon for the upper (or aircraft) antenna is
(1) determined from the facility horizon obstacle (common horizon) or
(2) taken as the smooth earth radio'horizon when a common horizon is negated by the earth's bulge.

The code included here incorporates a handful of local modifications that were made to
the original code published in FAA·RD-73-103.

A second report (DOT/FAA/ES-83/3) is also included for reference. It describes the IF-77
Electromagnetic Wave Propagation Model, which improves on the 1973 model used here.

