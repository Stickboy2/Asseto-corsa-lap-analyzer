# Asseto-corsa-lap-analyzer

AC LAP ANALYZER
===============
Free lap analysis for Assetto Corsa. Records your laps live, then shows:
  - a track map with every lap and "ghost cars" you can play back
  - speed / throttle / brake / steering traces with delta time
  - per-corner brake point, entry / apex / exit speed, throttle pickup, steering
  - the corners where you lose the most time, with coaching tips

Everything runs on your own PC. Nothing is uploaded anywhere.


WHAT YOU NEED
-------------
  - Windows PC with Assetto Corsa (the original game)
  - Python 3.8 or newer, free from https://www.python.org/downloads/
    (during install, tick "Add Python to PATH")
  - A web browser
No other packages to install.


SET UP (2 minutes)
------------------
  1. Unzip this folder anywhere (right-click > Extract All). Don't run it from inside the zip.
  2. Double-click  start.bat
     A black window opens and your browser goes to http://localhost:8765.
     Keep the black window open while you drive.
  3. If Windows Firewall asks, click Allow (it only listens on your own PC).


RECORDING LAPS
--------------
  1. Start Assetto Corsa and get on track (a live session, not a replay or the menu).
     The order of starting the game and this tool doesn't matter.
  2. In the browser, click  "Record live".
  3. Cross the start/finish line. That begins a clean lap.
  4. Drive a full lap and cross the line again. The lap is saved.
     (The lap you press Record on is skipped, and laps through the pits are skipped.)
  5. Do as many laps as you like, then click  "Pause & analyze".

Recorded laps live in the browser page only. Refreshing the page loses them.

Pick which lap to analyze and which to compare against with the two dropdowns.
By default it compares your latest lap against your fastest.
Map: scroll or pinch to zoom, drag to pan, double-click to reset. Press Play to watch the ghost cars.


TROUBLESHOOTING
---------------
  "Python was not found"      Install Python and tick "Add Python to PATH". If it still fails,
                              Windows may be using the Microsoft Store shortcut: search
                              "Manage app execution aliases" and turn off the python.exe ones.
  "Port 8765 is already in use"  Close the other black window and start again.
  Status says "waiting for a live session"  Get on track in AC (not paused, not in a replay).
  Page says live recording needs the local bridge  You opened a copy of the page directly or
                              from the web. Use http://localhost:8765 with start.bat running.
  Steering numbers look odd   The tool guesses AC's steering units.
  Nothing saved after one lap You must cross the line twice after pressing Record (see above).

Want to just look around first? Double-click ac_lap_analyzer.html to open the demo laps.
Live recording doesn't work that way; it needs start.bat.


FILES
-----
  start.bat               double-click to run
  ac_live_server.py       reads the game's telemetry and serves the page
  ac_lap_analyzer.html    the analysis page
