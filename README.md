# AI Particle Shaper

An interactive 3D particle simulation that responds to hand gestures using MediaPipe and Three.js. Control thousands of particles with your hand movements to create mesmerizing shapes and effects.

![Hand-Tracked Particle Simulation](https://img.shields.io/badge/Status-Active-success)
![Three.js](https://img.shields.io/badge/Three.js-v0.160.0-blue)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Hands-orange)

## ✨ Features

- **Real-time Hand Tracking**: Uses MediaPipe Hands for accurate hand detection and gesture recognition
- **4,000 Interactive Particles**: Smooth, GPU-accelerated particle system with dynamic colors
- **Multiple Shapes**: Switch between 5 different particle formations:
  - 🔮 Sphere
  - ❤️ Heart
  - 🌸 Flower
  - 🪐 Saturn
  - 🌪️ Tornado
- **Gesture Controls**:
  - 👋 **Move Hand**: Position the particle system in 3D space
  - 👌 **Pinch**: Expand or contract the particles
  - ✊ **Fist**: Cycle through different shapes
- **Dynamic Visuals**:
  - Auto-rotating shapes
  - Color transitions based on hand position and spread
  - Fog effects for depth
  - Glowing particle effects with additive blending

## 🎮 Controls

| Gesture | Action |
|---------|--------|
| **Open Hand Movement** | Move the particle system around the screen |
| **Pinch (Thumb + Index)** | Expand particles outward (wider pinch = more expansion) |
| **Fist** | Switch to next shape (cooldown: 1 second) |
| **Wide Spread Fingers** | Accelerate color transitions |

## 🚀 Getting Started

### Prerequisites

- A modern web browser with WebGL support (Chrome, Firefox, Edge, Safari)
- A webcam
- HTTPS connection (required for webcam access) or localhost

### Installation

1. Clone this repository:
```bash
git clone https://github.com/Sneha73685/particle-simulation.git
cd particle-simulation
```

2. Serve the file using a local web server. Choose one of these methods:

**Using Python:**
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

**Using Node.js (http-server):**
```bash
npx http-server -p 8000
```

**Using VS Code:**
- Install the "Live Server" extension
- Right-click on `index.html` and select "Open with Live Server"

3. Open your browser and navigate to:
```
http://localhost:8000
```

4. Grant camera permissions when prompted

## 🛠️ Technical Details

### Technologies Used

- **Three.js (v0.160.0)**: 3D graphics and particle system
- **MediaPipe Hands**: Real-time hand tracking and gesture recognition
- **Vanilla JavaScript**: No build tools required

### Architecture

- **Particle System**: 4,000 particles with BufferGeometry for performance
- **Shape Morphing**: Smooth transitions using linear interpolation (lerp)
- **Gesture Detection**:
  - Position tracking via index finger tip (landmark #8)
  - Pinch detection using thumb-index distance
  - Fist detection based on finger folding relative to wrist
- **Color System**: HSL color space with dynamic hue rotation
- **Rendering**: WebGL with additive blending for glow effects

### Performance Optimizations

- Efficient BufferGeometry for particles
- Pixel ratio capped at 2x for high-DPI displays
- Reduced camera resolution (320x240) for faster processing
- Smooth interpolation to prevent jittery movements

## 📁 Project Structure

```
particle-simulation/
├── index.html          # Main application file
└── README.md          # Project documentation
```

## 🎨 Customization

You can modify these constants in the code to customize the experience:

```javascript
const PARTICLE_COUNT = 4000;      // Number of particles
const PARTICLE_SIZE = 0.15;       // Size of each particle
const SHAPES = ['sphere', 'heart', 'flower', 'saturn', 'tornado']; // Available shapes
```

### Adding New Shapes

To add a custom shape, add a new case in the `calculateTargets()` function:

```javascript
else if (shapeType === 'myShape') {
    // Your parametric equations here
    x = // x coordinate
    y = // y coordinate
    z = // z coordinate
}
```

## 🐛 Troubleshooting

**Camera not working:**
- Ensure you're using HTTPS or localhost
- Check browser camera permissions
- Try refreshing the page

**Poor performance:**
- Reduce `PARTICLE_COUNT` in the code
- Close other browser tabs
- Ensure hardware acceleration is enabled

**Hand tracking not responsive:**
- Ensure good lighting conditions
- Keep hand within camera frame
- Try adjusting `minDetectionConfidence` and `minTrackingConfidence` values

## 🌐 Browser Compatibility

- ✅ Chrome/Edge (Recommended)
- ✅ Firefox
- ✅ Safari (macOS/iOS 14.5+)
- ⚠️ Requires WebGL and WebRTC support

## 📝 License

This project is open source and available for educational and personal use.

## 🙏 Acknowledgments

- [Three.js](https://threejs.org/) - 3D graphics library
- [MediaPipe](https://mediapipe.dev/) - Hand tracking solution by Google
- Inspired by creative coding and interactive art

## 🔮 Future Enhancements

- [ ] Add more gesture controls (rotate, scale)
- [ ] Custom particle textures
- [ ] Save/export animations
- [ ] Multi-hand support
- [ ] Additional particle shapes
- [ ] Performance mode toggle
- [ ] Touch screen support for mobile

## 👩‍💻 Author

Sneha73685

---