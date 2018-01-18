TerrainLOS

TerrainLOS is a propagation model (Radio Medium in COOJA terminology) that uses 
Digital Elevation Models (DEMs) to determine whether two nodes can communicate.
To learn more about TerrainLOS visit inrg.soe.ucsc.edu/?project=terrainlos.

Installation instructions:

1. Install Contiki/COOJA

TerrainLOS is implemented for COOJA a Contiki network simulator (contiki-os.org).
In order to use TerrainLOS you must first have a working copy of Contiki
and COOJA, please follow a guide at this link (contiki-os.org/download.html).
If this is your first time using Contiki and COOJA I highly recommend 
downloading Instant Contiki, a virtual machine that contains all the necessary
setup.

The Contiki source code is managed using Git. There are multiple versions of Contiki/COOJA, 
which are differentiated based on a Git Branch. You can see a list of all branches by
using the Git command:
  >> git branch -r

You can then switch to the designated branch using the Git command Checkout, for example to
switch to the 2.7 version use the command:
  >> git checkout release-2-7

2. Download TerrainLOS

Clone the TerrainLOS repo from Github and place it wherever you desire. COOJA
uses ant to build and run, so in this vein we also use ant to build and run
TerrainLOS.

Make sure you also switch to the same version that you are using in Contiki/COOJA. You
can also use the same Git Branch and Git Checkout commands to view the branches and
switch branches.

3. Configure COOJA to recognize TerrainLOS

By default COOJA will not recognize the TerrainLOS project. To add TerrainLOS as
a project run COOJA, for instance when in the COOJA directory (contiki/tools/cooja)
type ant run to open the COOJA GUI. Click on the Settings->Cooja Extensions menu
option. This will open a window and allow you to select the TerrainLOS directory
as COOJA project directory. Once selected hit the Save button. This will add
the TerrainLOS project to a user configuration file and everytime COOJA is run
it will also load TerrainLOS.

4. Build and Test TerrainLOS

After configuring COOJA you must build TerrainLOS this can all be done using Ant, but
before TerrainLOS can be built you must set the path to COOJA (by default it is set
to ~/contiki/tools/cooja). The path can be set in the build.xml file under the property "cooja".
To build navigate to the TerrainLOS directory previously downloaded and use
the command:
  >> ant jar

To test that TerrainLOS is correctly installed use the command:
  >> ant test
