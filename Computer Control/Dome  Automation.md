Originally the observatory was in the garden of Pitton Mill Cottage Rhossilli
It went through a few designs from starting as the converted Wendy house, to the roll off roof, then the polycarbonate dome which leaked and then the custom fibreglass coated cardboard which distorted badly.






**Use of SGPro Sync function** in Observatory panel:

Sometimes the dome is not correctly synced so I asked Copilot AI about use of the sync function:
**Q**
So if my telescope is correctly pointing at an object but the dome aperture is misaligned by 15 degrees how can the sync function help me?
**A**
If your telescope is correctly pointing at an object but the dome aperture is misaligned by 15 degrees, the **Sync** function in Sequence Generator Pro's Observatory panel can help by aligning the dome's reported azimuth with its actual physical position. Here's how you can use it:

1. **Manually Adjust the Dome**:
    
    - Rotate the dome manually so that the aperture aligns perfectly with the telescope's field of view. (PK addition - have to unslave to do this or ASCOM will realign)
        
2. **Use the Sync Function**:
    
    - Once the dome is correctly aligned with the telescope, click the **Sync** button in the Observatory panel.
        
    - Enter the dome's current azimuth angle (as it should be based on its physical position). For example, if the dome is physically pointing at 0° (north), input 0°.
        
3. **Update the Dome's Azimuth**:
    
    - The Sync function will update the dome's internal azimuth reading to match its actual position. This ensures that the software and the dome are in sync.
        
4. **Enable Slaving**:
    
    - If you have the "Slave to Telescope" option enabled, the dome will now move correctly to follow the telescope's movements, keeping the aperture aligned.
        

By syncing the dome's azimuth to its true position, you correct any discrepancies between the dome's reported position and its actual orientation. This ensures accurate alignment for the rest of your session. Let me know if you'd like further clarification!





return to [[Observatory Home]] home page