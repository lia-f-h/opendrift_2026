OpenDrift version with adaptions from my doctoral studies (add link). The adaptions include:

 - Modified sea-ice-drag formulations with flexible threshold for a lock-in, and a concentration-dependent sea-ice-drag coefficient. The lock-in threshold default is set to 0.7 (before: 0.9), in line with small Arctic icebergs.
 - Switches to disable the drag by sea ice, water and wind, similarly to what was implemented for wave_rad. The default is set to True, so that the drag is automatically enabled, but can be set to False by expert users.
 - The initial iceberg velocity is set to the velocity of sea ice in concentrations larger the threshold of iceberg lock-in. It is also set to the sea ice velocity when the initial velocity would be zero otherwise due to missing current, input, stokes input (which are usually used to calculate the initial velocity), the sea-ice-drag is enabled, and the concentration is larger 15%.

Also:
 - The fallback values of water, wind and sea ice velocities are set to zero (instead of None) for using switches for drag processes suggested above.
 - Default for wave_rad is set to False to disable highly unreliable wave forces. The default of stokes_drift is set to True as it proved to contribute significantly in one of the studied cases. The default of melting is set to True, as most iceberg drifts are impacted by melting.

The adaptions were applied on a forked version of https://github.com/OpenDrift/opendrift in April 2026. Find documentation and installation instructions on https://opendrift.github.io/install.html
