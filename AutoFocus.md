
In SGP help there is a great tutorial [here](https://help.sequencegeneratorpro.com/UnderstandingAutoFocus.html) use this to set up the autofocus criteria and star detection. Enlarge the text with Ctrl + etc as normal

# Backlash estimation
From Copilot AI:
### Steps to Determine Backlash Compensation:

1. **Measure Backlash**:
    
    - Use the MicroTouch focuser to move the fine focus shaft in one direction until the primary mirror starts to move.
        
    - Reverse the direction and count the number of rotations or steps required before the mirror begins moving again. This is your backlash.
        
2. **Set Backlash Compensation**:
    
    - Once you know the number of rotations or steps needed to overcome backlash, configure the MicroTouch focuser or your software (e.g., SGPro) to account for this during focusing routines.

Also from Copilot AI
### **Choosing the Correct Direction:**

1. **Primary Mirror Movement (SCTs)**:
    
    - For telescopes like your C14, where the focuser moves the primary mirror, backlash compensation is typically set to **IN**. This ensures that the mirror is always pushed against gravity or mechanical slack, reducing mirror shift.
        
2. **Test and Observe**:
    
    - If you're unsure, test both directions. Run an autofocus routine and observe the results. The correct direction will produce a smoother and more consistent "V-curve."
        
3. **General Rule**:
    
    - Choose the direction that ensures the final focus adjustments are always made in the same direction, avoiding any "dead zone" caused by backlash.