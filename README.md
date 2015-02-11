Snap! V-REP example
===================

Install V-REP
-------------

Download from http://www.coppeliarobotics.com/downloads.html


Copy DLL for API
----------------

Copy 2 files (Python wrapper and constants for API) from folder `[Program Files]\V-REP3\V-REP_PRO_EDU\programming\remoteApiBindings\python\python`:


* `vrep.py`
* `vrepConst.py`

Copy `remoteApi.dll` from `[Program Files]\V-REP3\V-REP_PRO_EDU\programming\remoteApiBindings\lib\lib\`, folder (according to your machine 32/64bit architecture):

* `32Bit`
* `64Bit`

To current folder.


Install Python
--------------

* Python27
* bottle

To install `bottle` in console:

    pip install bottle

`bottle` - is web framework.


Start API backend
-----------------

In console:

    python snap_vrep_backend.py 

Bottle started at `8080` port.

Start V-REP
-----------

Start V-REP and open `scena/simpleLineFollower_api.ttt` file.

It's simple LineFollower (without Lua embedded script).

Start Simulation by press on "Play" button.

Test API web control
--------------------

Open in browser URL:

* http://localhost:8080/up
* http://localhost:8080/down
* http://localhost:8080/left
* http://localhost:8080/right


See moving of LineFollower at V-REP. If not moving see section "Problems".


Start Snap!
-----------

Open demo Snap! application: http://snap.berkeley.edu/snapsource/snap.html#cloud:Username=nemilya&ProjectName=v-rep_demo

Or open: http://snap.berkeley.edu/snapsource/snap.html and Drag and drop file `v-rep_demo.xml` to browser.

Press curson up/down/left/right - see reaction of car at V-REP

Press "w", "a", "d" keys - see reaction of car at V-REP.

In Snap! was created custom blocks: "up", "down", "left", "right". Each block just call "Report" block, with URL request (to `http://localhost:8080/ACTION`).



Problems
--------

* Q: Car not moved? 
* A: Are you pressed "Play" button for start simulation at V-REP?

* Q: Python backent cant connect to `19997` port (in `snap_vrep_backend.py`)?
* A: See config `portIndex1_port` in `V-REP_PRO_EDU/remoteApiConnections.txt`