[[Observatory Home]]  NINA Home [[NINA]]
**Q to AI**
here's a problem I'd like help with in NINA. If for instance i were to image a nebula or galaxy which fills the small fov, platesolving often fails. So I need a centreing process that goes to the object, moves away by say 30 arcmin, does a platesolve and if successful moves back to the target. If not successful move another 30 arcmin & try again. Three iterations in total to try to get a PS and move to target.

## Copilot said

That’s a clever workaround—and yes, you can build this logic into NINA’s **Advanced Sequencer** using a combination of **slew**, **offset**, **plate solve**, and **conditional branching**. Here’s how to structure it:

## 🧠 Goal

When imaging a large nebula or galaxy that fills your small FOV:

- Slew to target
    
- Offset by 30 arcmin
    
- Try plate solve
    
- If successful → return to target
    
- If not → offset again (up to 3 tries)
    

## 🛠️ How to Build It in NINA's Advanced Sequencer

### 🔁 Step Group: “Plate Solve Offset Loop”

Use a **Repeat Until** block with a **counter** and a **success flag**.

### 1. **Set Variables**

- `OffsetCount = 0`
    
- `PlateSolveSuccess = false`
    

### 2. **Repeat Until**

Condition: `OffsetCount >= 3 OR PlateSolveSuccess = true`

Inside this loop:

#### ➤ Slew to Target

- Use the **Target Set** coordinates
    

#### ➤ Offset Position

- Use **Slew Offset**: e.g., +30 arcmin in RA or Dec (you can alternate directions if needed)
    
- Increment `OffsetCount`
    

#### ➤ Plate Solve

- Use **Center Scope** or **Solve and Sync**
    
- If successful → set `PlateSolveSuccess = true`
    

#### ➤ If PlateSolveSuccess = true

- Slew back to original target coordinates
    

## 🧪 Optional Enhancements

- Add a **Wait** step between retries to allow mount settling
    
- Log each attempt for debugging
    
- Use **Trigger** blocks to handle failure gracefully
    

Would you like me to sketch out the exact sequence steps or help you build a reusable template for this logic? I can also help you test it with a dummy target.