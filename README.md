# Software for the Quantum Technologies Teaching and Test-Bed (QT3) Laboratory

This provides a brief overview of the Python-based software available to run
experiments in the QT3 Lab. These tools were developed for the confocal
microscope and its specific set of hardware. However, many of these
components should be reusable on other microscopes with similar setups.

### Goals

There were a number of development goals when the QT3 software construction began.

  * Python package delivery
  * foundational API for extended development by lab and community members
  * well written documentation
  * basic GUI applications

## Hardware

The programmable hardware currently used on the confocal microscope in QT3 (Sep 2022) are

  * National Instruments PCIx-6363 data acquisition card (NIDAQ)
  * Windfreak PRO RF Synthesizer (microwave source)
  * Quantum Composer Sapphire 4-channel TTL pulse generator
  * Spin Core Pulse Blaster

Additionally, the Jena Systems's Piezo Actuator stage can be controlled via
the NIDAQ, and switches for an AOM and microwave amplifier can be controlled
via TTL pulses.

The Excelitas SPCM is the photon detector used in the lab. The SCPM produces a 50 ns
TTL pulse upon the detection of a photon. The TTL pulse is connected via BNC to
a digital input channel on the NI-DAQ. The `qt3utils` software configures readout of this
digital input channel and can return raw counts as well as count rate. Since the SPCM
couples to the NIDAQ via TTL pulses over BNC, any other photon detector that produces
the same signal can be utilized.

Finally, to ensure robust data acquisition, TTL pulses are generated to provide a clock and
trigger of the NIDAQ. (As of now, only the QC Sapphire is programmed for performing this.)

## Overview of Packages

The following packages have been developed

* [qt3utils](https://github.com/gadamc/qt3utils)
* [qt3RFSynthControl](https://github.com/gadamc/qt3RFSynthControl)
* [qcsapphire](https://github.com/gadamc/qcsapphire)
* [nipiezeojenapy](https://github.com/gadamc/nipiezeojenapy)
* [pulseblaster](https://github.com/zeeshawnkazi/pulseblaster)

### QT3-Utils

The [`qt3utils` package](https://github.com/gadamc/qt3-utils) is the primary package
that experimenters will interact with directly. The `qt3utils` package provides

  * NIDAQ configuration (via `nidaqmx`)
  * high level objects for data acquisition
    * raw data sampler
    * piezo scanner
  * "canned" experiment objects (CWODMR, Rabi, pulsed-ODMR, etc)
  * GUI applications
    * qt3scope
    * qt3scan

##### GUI Application: QT3Scope

The `qt3scope` measures the count rate to a digital input channel on the NIDAQ as a function of time
(and appears as an oscilloscope that is measuring a voltage that is proportional to the count rate)

![QT3Scope](qt3scope.png)

## Next Steps

1. Verify naming of objects and applications
2. Build laser power monitoring / control package
3.
