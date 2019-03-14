## Scripts

tools for the analysis of the radio continuum emission of a radio AGN.

***
**Requirements**

`radiobs` needs to be in your PYTHONPATH.

***
***

**Core-pbCorrCvRegr**

- Corrects for a gaussian primary beam of different telescopes
- Convolves to a common synthesized beams
- Regrids a set of images to a common synthesized beam and frame of reference.

_It does not conserve the flux per pixel_: use `SYNAGE++` for the same routine. Probably because input images are in JY/Beam, while they should be in the following units: Jy, YJy, ZJy, yJy or zJy? [mpdaf.obj.data]
  
Used for the core/jet structure of the radio source.

***

**Core-Fluxes**

Measures the flux of the core/jet structure from a list of images (typically the pbcorr/convolved/regridded images from above)

Saves to tables: 
- integratedFluxes.tbl'
- synageFlCore.tbl -> readable by `SYNAGE++`

After running synage on the total flux density distribution of the two components.

Plots:
- Core/Jet flux density distribution
- Core/Jet CI + CIOff overlays
- Core CI + CIOff * Jet CI + CIOff 

***
**Core-plots**

Plots the innermost region of the radio source at different frequencies using aipy.

***
**Lobes-Fluxes**

Measures the flux density of different components of a radio source (provided ds9 regions) at various frequencies.

Outputs tables in `ascii` and `SYNAGE++` format.

***
**Lobes-Flux-ratio**

Estimates the flux ratio betwen E/W radio lobes at different frequency.
Estimates the ratio between the radii of the E/W radio lobes given a spectral index (and assuming adiabatic expansion).

***
**SED-plots**

Plots flux density distribution for different component of the radio source

- Flux density = model of singularly E,W,T: `ToT_CICIOFF.png`, `WLobe_CICIOFF.png`, `ELobe_CICIOFF.png`,`Core_CICIOFF.png`
- Flux density of E,W,T overlayed: `sed_All.png`
- Flux density + model of E,W,C,J overlayed: `modAll1.png`
- Flux density + model of single pixel: `pix_39_41.png`


***
**SED-stats**

Determines different physical quantities given the results of `SYNAGE++` analysis.

- Synchrotron age and off time.
- B of equipartition
- Buoyancy time
- Radio power of different source components
- Plots Magnetic field vs source age: `tSyncOverTbuoyLobes.png`

***
**Noise**

Measures noise in _Planck_ images and saves them to a table.

