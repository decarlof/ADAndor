=============
Configuration
=============

The Andor driver is created with the andorCCDConfig command, either from C/C++ or from the EPICS IOC shell.

 

The Shamrock driver is created with the shamrockConfig command, either from C/C++ or from the EPICS IOC shell.

::

        int andorCCDConfig(const char *portName,
                        int maxBuffers, size_t maxMemory,
                        const char* installPath,
                        int priority, int stackSize)


The Shamrock driver is created with the shamrockConfig command, either from C/C++ or from the EPICS IOC shell.


::
      
        int shamrockConfig(const char *portName, 
                          int shamrockId, const char *iniPath, 
                          int priority, int stackSize)
  

For details on the meaning of the parameters to this function refer to the detailed documentation on the andorCCDConfig function in the shamrock.cpp documentation and in the documentation for the constructor for the shamrock class.

There an example IOC boot directory and startup script (iocBoot/iocAndor/st.cmd) provided with areaDetector. 

.. contents:: Contents:
   :local:

