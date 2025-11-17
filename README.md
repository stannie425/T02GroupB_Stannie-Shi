# T02GroupB_Stannie-Shi

## Part1: How to Interact
1. Click anywhere on the canvas once to activate the audio engine (required for unlocking the Web Audio API via `userStartAudio()`).
2. Hover over `Circle 1`(Purple)/ `Circle 2`(Orange-Green) / `Circle 8`(Green Dots) to preview sound.
3. Move the cursor away to stop playback.
4. Click an interactive circle to lock or unlock continuous playback.
5. Drag horizontally (while hovering or locked) to adjust the audio playback rate and rotation speed.
6. Only Circles 1, 2, and 8 rotate during audio playback; other circles remain static to preserve the visual composition.

## Part2: Individual Animation Approach
For my contribution, I used audio as the driving mechanism. The disc-like circular forms make sound-driven rotation a natural extension of the visual concept.

My approach links:
- audio playback
- rate control
- dynamic filtering
- rotation

My component establishes a direct connection between sound and motion.

## Part3: Animated Properties

### Interactive Rotation
- Circles 1, 2, and 8 rotate when audio plays.
- Rotation speed matches playback rate, mimicking turntable behaviour.

### Filter-Based Sonic Identity
Each interactive circle applies a distinct filter:
- Circle 1 → High-pass filter
- Circle 2 → Band-pass filter
- Circle 8 → Low-pass filter

This gives each circle a unique sonic character.

### Static Non-Interactive Circles
All other circles remain still to preserve the structural balance of the original artwork.

## Part4: Inspiration
Inspired by vinyl records and DJ turntable performance:
- continuous rotation during playback
- pitch shifts when adjusting platter speed
- tonal shaping similar to DJ EQ filtering
- hover-trigger playback reminiscent of a stylus touching the record
![Vinyl](./assets/vinyl%20records.jpg)



## Part5: Technical Explanation

### Audio System
- Audio starts only after a user click via userStartAudio().
- A `p5.Filter()` node shapes the sound, switching type according to the active `circle (1 / 2 / 8)`.

### Interaction Logic
- `getCircleIdAt()` handles hit detection for the three interactive circles.
- Hover → start loop; leave → stop playback.
- Click toggles a lock for hands-free playback.
- Drag maps mouse movement to `vinylSound.rate()`, affecting pitch and rotation speed.

### Rotation System
- `circleRotation[id]` stores rotation angles for the interactive circles only.
- Angles update during playback; `noLoop()` ensures the canvas redraws only on state change.

### Rendering Efficiency
- The sketch uses `noLoop()` to avoid unnecessary rendering.
- Visual updates occur only when interaction changes (hover, lock, drag, rate).

## Part6: Modifications to Group Code
Visual functions (drawCircle1–8) remain unchanged.
My contributions include:
- the entire audio system (sound loading, filters, rate control)
- hover / click / drag interaction logic
- rotation behaviour for selected circles
- small update to `CircleArt.display()` to apply rotation
- additional state variables for audio-driven animation



