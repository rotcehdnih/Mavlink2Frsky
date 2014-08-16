Mavlink2Frsky
=============

Converts Mavlink packets to Frsky S.Port Using Software serial 

Based on the work of Rolf Blomgren this is just a small edit to allow use for any Arduino not just Teensy's.

Lost acclx in exchange for GPS H.Dop 


Also added some fixed by "chsw" - Christian

- Acc X/Y/Z reports the average vibrations (difference between max/min) instead of actual accelerometer values.
- Reports gps-speed instead of hud-speed.
- Change how the code responds to tx telemetry requests. This fixes the missing cell/cells in the latest open-tx versions.
- Updated the cell detection to minimize the risk of detecting to many cells (unless the battery is low upon connection)
  and changing the cell count inflight when the battery voltage drops.
- Changed the averaging for voltage/current to be more accurate to the voltage/current fluctuations. Hoping of increasing the 
  accurasy of the mAh-counter. Use FAS as both voltage/current source.
- Delays sending the voltage/current until the voltage reading through mavlink has stabilized. This should minimize the false 
  low battery-warnings upon model powerup.
  

connect the S.port data line to D9 

