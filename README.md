# Pick A Gift — AR

A risograph-style web AR experience for giving a gift and a feeling.

Three identical gift cards float in front of your face. Point at one with your finger and hold it there to open it:

- **Birthday cake**: cake slices rain down and pile up around your body, with a fanfare and "Happy Birthday!" written in ribbon above your head.
- **Snacks**: bags of Cheetos, Doritos, Lay's, Oreo and Nerds fall and stack around you, with "It's All Yours!" in sparkling letters.
- **Cash**: bills fly in from the sides and stick to the walls, the floor and you, while a slot machine above your head lines up $ $ $.

**Live:** https://suyoungkwon2.github.io/pick-a-gift-ar/

## How it works
- The laptop webcam or the phone's front camera (`facingMode: 'user'`), mirrored.
- [MediaPipe Tasks Vision](https://developers.google.com/mediapipe): Pose Landmarker (face and body) and Hand Landmarker (index fingertip).
- [Matter.js](https://brm.io/matter-js/) physics. The tracked head, torso and arms become colliders, so falling items slide off the person and pile up around them.
- Everything is drawn on a canvas in a limited riso ink palette (fluorescent pink, blue, yellow and green), with overprint, misregistration, halftone and paper grain. The camera feed is rendered as a two-colour riso print.
- Sounds are synthesised with the Web Audio API. No assets are needed.

## Run locally
Camera access needs `https` or `localhost`. Open it in Chrome:

```
python3 -m http.server 8765
# then open http://localhost:8765
```

Add `?demo` to preview without a camera, or `?debug` to see the body colliders.
