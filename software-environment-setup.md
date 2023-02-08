# QT3 Quantum Light Microscope

The following instructions are for setting up the QLM microscope machine
with the QT3 software.

These instructions should also work for other setups that use similar hardware.

We utilize Anaconda for managing our python environments.

### Install Anaconda

First, one should install Anaconda if it's not already installed.

Launch Anaconda.

### Create New Environment.

If you are simply a user of the code,
that environment may be called something like "qt3-production" to indicate
that you are using the "production" level qt3 code and do not intend to
develop new features or fix bugs.

If you need to develop new code for
one of the qt3 software repositories, a better environment name may be "qt3-develop-feature-X",
or similar, depending on your project and scope.

In either case, the QLM also needs some external divers.
If you are setting up a new machine from scratch, you will
need to install these. If you are a user on the QLM machine that is already in
use, these drivers are likely already installed.

* [National Instruments DAQmx](https://nidaqmx-python.readthedocs.io/en/latest/)
  * [driver downloads](http://www.ni.com/downloads/)
* [SpinCore's PulseBlaster](https://www.spincore.com/pulseblaster.html)
  * [spinAPI driver](http://www.spincore.com/support/spinapi/)

#### Production Environment Setup

Once the NIDAQ and SpinCore drivers are installed, installation of the python
software should be straight forward from the command-line.

1. Open Anaconda
2. Activate your production environment
3. Launch a Powershell
4. Ensure the powershell prompt displays the correct environment name
5. Use pip to install
  * `> pip install qt3-utils`

If installation is successful, you should be able to run the GUI applications
defined in [qt3-utils](https://github.com/qt3uw/qt3-utils).

The powershell is recommended at this time because we do not have automatic
application deployment. Also, running the GUI applications from the Powershell
provides a stdout for the application to set log messages. These log messages
are useful as a user to see that the application is running and this is where
messages will be displayed when errors occur.

#### Develop Environment Setup

Once the NIDAQ and SpinCore drivers are installed, installation of the python
software should be to simply run `pip install qt3-utils` from the command-line

1. Open Anaconda
2. Activate your production environment
3. Launch a Powershell
4. Ensure the powershell prompt displays the correct environment name
5. Navigate to a location on the filesystem where you want to perform development
  * For example, `> mkdir \Users\YOURNAME\projects; cd projects`
6. Clone the git repository of interest.
  * For example `> git clone https://github.com/qt3uw/qt3-utils`

Development after this step is up to you. You can install PyCharm or VSCode from
Anaconda, or work with something lighter like Atom.


#### Laser Power Control

Control of laser power via ND filter wheel is done using 
[qt3laserpowercontrol](https://github.com/qt3uw/qt3laserpowercontrol). This software 
controls an ARDIUNO board that is connected via USB. The software needs to be 
installed onto the ARDUINO board and then launched separately from the command line.

##### Production Conda Environment Snapshots

The following links to minimal conda environments on the QLM machine that were 
known to work. These environments pin down specific versions of software and should 
be able to recreate environments

* [Feb 8 2023](qt3prod_2023_Feb_8.yaml)
