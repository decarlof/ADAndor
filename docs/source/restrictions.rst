============
Restrictions
============

The following are known restrictions of the Andor driver. These should be fixed in a future release.

    No support for detector output signals (trigger and gate).
    Some Andor detectors (including the iKon) only support a single period when doing multiple accumulations in kinetic series mode. For these cameras ANDOR_ACCUMULATE_PERIOD has no effect, ACQUIRE_PERIOD determines the time between accumulations, and the time between images is 0, i.e. the next image starts as soon as the previous one is complete.
    Saving files using the Andor driver in Multiple and Continuous modes results in errors because the Andor SDK functions won't save files if acquisition is in progress. Saving files in Single mode and Fast Kinetics mode works fine.
    Trigger modes have not been tested.
    The Shamrock wavelength calibration is only saved in SPE files. The Andor SDK file writers do not save the calibration, and it is not possible to pass the calibration to other file plugins as an attribute because array attributes are not currently supported in areaDetector.
    Single-Track, Multi-Track and Random-Track readout modes are not yet supported.


.. contents:: Contents:
   :local:

