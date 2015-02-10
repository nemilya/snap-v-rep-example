Snap! V-REP example
===================

Install V-REP
-------------

Download from http://www.coppeliarobotics.com/downloads.html


Copy DLL for API
----------------

Copy files from `[Program Files]\V-REP3\V-REP_PRO_EDU\programming\remoteApiBindings\python\python`


* vrep.py
* vrepConst.py

Copy `remoteApi.dll` from "[Program Files]\V-REP3\V-REP_PRO_EDU\programming\remoteApiBindings\lib\lib\", folder:

* 32Bit
* 64Bit

To current folder.


Install Python
--------------

* Python27
* bottle

    pip install bottle

bottle - is web framework.


Start API backend
-----------------

    python snap_vrep_backend.py 

Bottle started at `8080` port.

Start V-REP
-----------

Start V-REP and open `scena/simpleLineFollower_api.ttt` file.

It's simple LineFollower without Lua embedded script.

Start Simulation by press on "Play" button.

Test API web control
--------------------

* http://localhost:8080/up
* http://localhost:8080/down
* http://localhost:8080/left
* http://localhost:8080/right


See moving or line follower at V-REP.


Start Snap!
-----------

Open: http://snap.berkeley.edu/snapsource/snap.html

Drag and drop file `v-rep_demo.xml`

Press curson up/down/left/right - see reaction of car at V-REP

Press w/a/d - see reaction of car at V-REP.

Custom blocks: up/down/left/right



Problems
--------

* Q: Car not moved? 
* A: Are user pressed "Play" button for start simulation at V-REP?

* Q: Port not connected `19997` (in snap_vrep_backend.py)?
* A: see config `portIndex1_port` in `V-REP_PRO_EDU/remoteApiConnections.txt`