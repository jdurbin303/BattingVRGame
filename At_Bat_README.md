# ⚾ At Bat — VR Baseball Batting

A room-scale VR batting game built in **Unity (C\#)** for the **Oculus Quest 2**: step into the box in a Coors Field environment and hit physics-accurate pitches. Built as my M.S. Computer Science graduate project (CU Denver) in Fall 2021\. 

🎥 **Gameplay video:** [https://youtube.com/shorts/YPkPa-3UDNs?feature=share](https://youtube.com/shorts/YPkPa-3UDNs?feature=share)

## Highlights

- **Physics-accurate pitching.** A launch-angle approach gave inconsistent speeds in Unity, so I set the ball's velocity directly from its components (v·cosθ, v·sinθ) — making exit velocity exactly match the target (15–55 mph). The ball is modeled to MLB regs (mass, size, drag), grounded in Adair's *The Physics of Baseball*.  
- **A real "sweet spot."** The bat is modeled as segments that each track their own velocity (Δposition / fixedDeltaTime), so the tip moves faster than the handle and *where* you make contact changes the hit — just like a real bat.  
- **Solving collision "tunneling."** At bat speed the ball would slip through the bat between physics frames (Unity's timestep vs. the Quest's frame rate). I wrote a predictive collision check that forecasts the ball's and bat's next-frame positions and forces the hit — backed by continuous collision detection and tuned colliders.  
- **DIY hardware.** The controller is a Quest controller mounted inside a cut-off foam bat; I calibrated the \~50° sensor-to-bat angle offset in Unity so the in-game bat tracks the real one. (A 3D-printed mount came first, but the toy bat was safer.)  
- **A real user study.** I designed and ran a 10-participant pilot — a 25-question, 5-point Likert survey plus gameplay observation and short interviews — testing whether tuning realism in the player's favor raised perceived realism and enjoyment. Results were positive on both and flagged where VR-specific challenges still needed work.

## Tech

`Unity` · `C#` · `Oculus Quest 2` · real-time physics · VR interaction

## A note on the source

I haven't uploaded the source code — a Unity/VR project's files (assets, the stadium environment, build artifacts) are very large. The gameplay video above is the best quick look; I'm happy to walk through the code and architecture directly.

*Coors Field 3D model by another CU Denver student; the game logic, physics, hardware rig, and study are mine.*  
