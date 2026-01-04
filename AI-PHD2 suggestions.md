back to  [[Observatory Home]]

for mesu 200, long focal length of 3128 (c14 with 0.8x reducer) and ASI 174mm mini guide cam:

AI7070
I’ll give you numbers you can actually plug into PHD2, tailored to your setup.

### 1. Your guiding scale

With ASI 174MM Mini (5.86 µm pixels) at 3128 mm:

scale≈206.265⋅5.863128≈0.39 arcsec/px

So 1 pixel ≈ 0.39″. That’s very fine sampling, which is great, but it also means seeing will dominate if you let PHD2 react too fast.

### 2. Exposure time

**Goal:** average out seeing, don’t chase it.

- **PHD2 exposure:** **Start with 2–3 s** If guide stars are faint in the OAG, use **3–4 s**.
    

Shorter than 2 s at this scale will mostly fight seeing, not real mount errors.

### 3. Calibration step size

This is the big one people get wrong at long focal length.
use the phd2 inbuilt calculator
    
### 4. Min‑move (RA and DEC)

At 0.39″/px with good seeing, you don’t want PHD2 correcting every tiny wiggle.

Start with:

- **RA min‑move:** **0.25 px** (≈ 0.1″) note phd2 default is 0.55 i kept that
     
- **DEC min‑move:** **0.25 px**  note phd2 default is 0.55 i kept that
    

If the RA graph looks noisy and “busy” (lots of small corrections), push both to **0.30 px**. If it looks too sluggish and RA drifts slowly, you can lower to ~0.20 px.

### 5. Aggressiveness

Your Mesu 200 is a very smooth mount; friction drive + no PEC means you generally want **gentle, smoothed corrections**, not aggressive ones.

- **RA Aggressiveness:** **60–70 %**
    
- **DEC Aggressiveness:** **50–60 %**
    

If you see oscillation (RA constantly over‑correcting around zero), reduce RA aggressiveness by 5–10 %.

### 6. Guiding algorithm choices

You can stay close to defaults, just tweaked:

- **RA algorithm:** **Hysteresis** (default) is fine. Hysteresis 10–20 %, Aggressiveness as above.
    
- **DEC algorithm:** **Resist Switch** is a good choice. If your DEC backlash is minimal (Mesu usually is very good), allow both directions. If you ever see DEC chasing backlash, consider “North only” / “South only” depending on your hemisphere.
    
- **Multi‑star guiding:** Leave it **ON** – it’s a real help at this scale.Open PHD Guiding
    

### 7. Mesu‑specific considerations

- **No PEC:** fine. The Mesu’s PE is already very low; you’re better off with smooth, moderate corrections than aggressively trying to “correct PE” that barely exists.
    
- **Guide rate:** if you can see the exact guide rate in SiTech, we could fine‑tune calibration step size more precisely, but the 250 - 300 ms range is a solid starting point.
    

### 8. How to refine after first night

Once you’ve dialled in the above:

1. Run the **Guiding Assistant** in PHD2 for 10–15 min on a star near dec 0 and meridian. It will:
    
    - Suggest min‑move
        
    - Show you mount backlash and RMS values
        
    - Confirm if you’re chasing seeing or notOpen PHD Guiding
        
2. Adjust min‑move and RA/DEC aggressiveness based on its suggestions.
    
3. Check your RMS:
    
    - On a good night, with your setup, **0.6–0.8″ RMS** is realistic.
        
    - Even **~1.0″ RMS** will be fine for most imaging with the C14, especially if you’re not oversampling on the main camera.