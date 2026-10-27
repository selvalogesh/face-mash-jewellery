# Face Mash Jewellery

A virtual necklace try-on that runs in the browser. Your webcam feed drives a jewellery
illustration in real time, so the necklace follows your neck and shoulders as you move.

**Live demo:** https://selvalogesh.github.io/face-mash-jewellery/ (allow camera access; pick a
necklace from the menu at the top right)

Built in July 2021 on top of Google's [Pose Animator](https://github.com/yemount/pose-animator),
which animates SVG illustrations from PoseNet and FaceMesh keypoints with TensorFlow.js.

## What I changed

- Four necklace illustrations (`gold`, `silver`, `silver2`, `stone`) in `resources/illustration/`,
  rigged to the Pose Animator skeleton, replacing the character avatars
- Full 800×600 camera canvas instead of the half-size preview, with the controls moved to the top right
- Mobile layout: the canvas scales to 80% of the screen and the video matches it
- Detection debug overlay off by default

See the second commit for the exact diff against the original project.

## Layout

| Path | What |
|---|---|
| `camera.html`, `camera.js` | The try-on page and its logic |
| `resources/illustration/*Neck*.svg` | Necklace illustrations |
| `docs/` | Production build served by GitHub Pages |
| `assets/unused/` | Draft necklace SVGs and downloaded reference images, kept for the record |
| `README-pose-animator.md` | Original Pose Animator README |

## Status

Archived. The `docs/` build is the 2021 production build. Rebuilding from source needs the old
Parcel 1 toolchain (`yarn && yarn build-camera` on Node 14), and Parcel 1 currently fails on the
npm `paper` 0.12 package, so treat the source as a reference.

## License

Apache License 2.0, same as Pose Animator. See [LICENSE](LICENSE).
