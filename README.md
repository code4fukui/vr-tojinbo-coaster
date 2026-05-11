# vr-tojinbo-coaster

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A virtual reality roller coaster experience built with Three.js and WebXR. Ride a dynamic track featuring a vertical loop, accompanied by ambient wind sounds that react to your speed.

## Demo

- **[VR東尋坊コースター](https://code4fukui.github.io/vr-tojinbo-coaster/)**

## Features

-   **Immersive VR Experience**: Enter a fully immersive 3D world with a WebXR-compatible browser and headset.
-   **Custom Roller Coaster Track**: The coaster follows a mathematically defined path using a custom `THREE.Curve` class, featuring a thrilling vertical loop and smooth transitions.
-   **Dynamic Wind Audio**: Utilizes the Web Audio API's `AudioWorklet` to create a realistic wind effect that changes in pitch and volume based on the coaster's velocity.
-   **Day/Night Mode**: Switch between day and night environments. In VR, this can be triggered by looking down while the coaster is stopped.
-   **Physics-Based Motion**: The coaster's speed is dynamically calculated in the animation loop, accelerating on descents and decelerating on inclines.
-   **Desktop & VR Controls**: Fully usable on a desktop with mouse and keyboard, or in a VR headset for a more immersive ride.

## Controls

### Desktop

| Action              | Control        |
| ------------------- | -------------- |
| Look Around         | Mouse Movement |
| Start / Stop Coaster| `Space` Key    |
| Toggle Day/Night    | `N` Key        |

*Click the screen to lock the mouse pointer for camera control. Press `Esc` to release.*

### VR Mode

| Action              | Control                                     |
| ------------------- | ------------------------------------------- |
| Start Coaster       | The ride begins automatically on entry.     |
| Toggle Day/Night    | While stopped, look down for 1.5 seconds.   |

*The coaster completes one lap and automatically stops at the starting point.*

## Technical Overview

-   **`TojinboCoaster.js`**: Defines the coaster's path, including the complex geometry and tangent calculations for the vertical loop section.
-   **`WindNode.js` & `wind-processor.js`**: Implements a custom `AudioWorkletNode` for high-performance audio processing. It loops a `.wav` file and adjusts its pitch and volume to simulate wind speed.
-   **`SkyGroundGeometry.js`**: A custom `BufferGeometry` that generates a sphere for the sky and flattens the lower hemisphere to create a ground plane, all within a single mesh.
-   **`models/sleeper.glb`**: A 3D model for the wooden railroad ties, loaded using `GLTFLoader`.

## Credits and Attribution

### Contributors

-   [taisukef](https://github.com/taisukef)
-   [stachiba0517](https://github.com/stachiba0517)
-   [84kaoru](https://github.com/84kaoru)

### Assets

-   **3D Model**: [Wood Stick 04](https://sketchfab.com/3d-models/wood-stick-04-b7fe8a4a3c2f4f038662ae47cfbfa6a7) by [3dhdscan](https://sketchfab.com/3dhdscan) is licensed under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/).
-   **Sound**: [VR東尋坊コースター 風の音 - Wind Outside](https://pixabay.com/ja/sound-effects/wind-outside-sound-ambient-141989/) from Pixabay.

### Reference Project

-   [VR東尋坊](https://code4fukui.github.io/vr-tojinbo/)

## License

MIT License.