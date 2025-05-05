We use ASTAP and ANSVR

# ANSVR

**Local Index file locations**
the ANSVR astrometry files are not stored in the normal location, they are in c:\astrometry\data

**Online index files**
https://data.astrometry.net/4200/

Note that the ANSVR index downloader no longer works :(

**ANSVR - from copilot**
### **Optimizing Index Files**

To limit ANSVR’s search time:

1. **Check the log files** after a few successful solves—see which index is being used consistently.
    
2. **Remove unnecessary indexes** that are clearly outside your field scale range.
    
3. **Keep one neighbouring scale index** (+1 and -1 step) in case of minor variations.
    
If your setup is stable, reducing the number of active index files should improve solving speed without compromising reliability. Have you checked which specific indexes are being used in your logs yet? That could help fine-tune your selection.

# ASTAP


**from Han at HNSKY:**
'You can keep triples on. It slow down a little but your field of view is small. It will switch automatically to quads if  more stars are detected. Just active triples and press once the solve button and ASTAP will remember the setting.

Maybe forcing binning to 3 helps for you. Just experiment. You only will get a warning "dimensions are too small". Just ignore it.'

As a blind solver, ASTAP will work if radius is set to 180 degrees. Normally have this set to 30 deg/

As a blind solve failover we use ansvr but it can be slow up to 8 minutes to solve. I am trying to optimise this by removing unused indexes.

ASTAP solved from SGP binning 3x3 in SGP one minute image on nuc starting 5-5-25 




