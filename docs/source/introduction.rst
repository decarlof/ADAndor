============
Introduction
============

This is an EPICS areaDetector driver for CCD detectors from Andor Technology using Version 2 of the Andor Software Development Kit (SDK). It has been tested on the Andor iKon and DU401 CCD cameras with USB interface, but should work with other cameras as well. The driver is supported on 32-bit and 64- bit Linux and 32-bit and 64-bit Windows.

The driver currently provides access to most of the features of the Andor cameras:

- All Andor acquisition modes (Single Scan, Accumulate, Kinetics, Run Till Abort, and Fast Kinetics
- Control of the exposure time, accumulate cycle time, and kinetic cycle time
- Support for all of the Andor trigger modes
- Support for all of the Andor shutter modes
- Support for reading the detectors with 16-bit or 32-bit depth
- Saving files using the Andor SDK and/or with the standard areaDetector plugins
- Change the ADC sampling speed (0.05MHz and 2.5MHz on the iKon)
- Set a region of interest (a smaller region can be read out faster)
- Set and monitor the CCD temperature
- Electron Multiplying (EM) Gain on supported detectors
- Support for selecting between Full Vertical Binning (FVB) and Image readout modes

The Andor module includes a separate driver to control the Andor Shamrock spectrographs. If the detector data is saved in the Princeton Instruments SPE file format using the Andor driver then it will include the Shamrock wavelength calibration information. No other file formats support saving the calibration.

This driver inherits from ADDriver. It implements many of the parameters in asynNDArrayDriver.h and in ADArrayDriver.h. It also implements a number of parameters that are specific to the Andor detectors. The Andor class documentation describes this class in detail.

This document does not attempt to explain the meaning of the Andor-specific parameters. The Andor Software Development Kit documentation provides this detailed information. Andor does not allow me to redistribute the SDK documentation as part of areaDetector. It must be obtained from Andor's Web site.

areaDetector includes the header and library files required to build the andor driver on any Linux or Windows computer. However, it does not include the shareable libraries, DLLs or drivers to actually run a detector. Those must be obtained from Andor, either by purchasing their SDK or their Solis application software. On Windows the path to the directory containing the Andor DLLs from the SDK or Solis must be added to the PATH environment variable when running the areaDetector IOC. On Linux the path to the directory containing the Andor shareable libraries from the SDK must be added to the LD_LIBRARY_PATH environment variable when running the areaDetector IOC.

NOTE: When using the Shamrock spectrograph on Windows the following DLLs must actually be copied from the SDK directory to the current working directory from which the IOC application is being run, e.g. iocBoot/iocAndor.

- atmcd32d.dll
- ShamrockCIF.dll
- atshamrock.dll

This is a rather strange requirement of the Andor Shamrock SDK, which will hopefully be fixed by them in a future release.

.. contents:: Contents:
   :local:

