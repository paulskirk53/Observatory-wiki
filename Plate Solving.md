We use ASTAP and it is good, but our FOV is small so PS is challenging because of small numbers of stars.

If the image does not solve due to poor star shapes, in ASTAP settings use triples instead of quads and set binning = 3 (downsample field)

**from Han at HNSKY:**
'You can keep triples on. It slow down a little but your field of view is small. It will switch automatically to quads if  more stars are detected. Just active triples and press once the solve button and ASTAP will remember the setting.

Maybe forcing binning to 3 helps for you. Just experiment. You only will get a warning "dimensions are too small". Just ignore it.'

As a blind solver, ASTAP will work if radius is set to 180 degrees. Normally have this set to 30 deg/

As a blind solve failover we use ansvr but it can be slow up to 8 minutes to solve. I am trying to optimise this by removing unused indexes.

**File locations**
the ansvr astrometry files are not stored in the normal location, they are in c:\astrometry\data


