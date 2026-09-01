# CS 4337 Interactive Visualizations

Browser demos that accompany the lecture slides and the Jupyter notebooks for
CS 4337, Introduction to Computer Vision.

Open [`index.html`](index.html) for the full list, or go straight to a lecture:

| Lecture | Folder | Demos |
| --- | --- | --- |
| 03, Motion Detection | [`03-motion-detection/`](03-motion-detection/) | 4 |
| 04, Thresholds, Morphological Operations and Filters | [`04-thresholds-morphological-operations-and-filters/`](04-thresholds-morphological-operations-and-filters/) | 10 |

## Running them

Double-click any `.html` file. That is the whole procedure.

Each page is a single self-contained document: the CSS, the JavaScript and any
images or video frames it needs are inlined into the file. There is no build
step, no package to install, no server to start and no network request, so the
pages work from a USB stick, from a folder on a lab machine, or from a laptop
with the wifi off.

The only external reference is a Google Fonts stylesheet. When it cannot be
reached the pages fall back to the system font stack and everything else keeps
working.

## What is in a page

Every demo follows the same shape:

- a **control rail** on the left, holding the parameters the lecture asks about
- a **stage** in the middle showing the effect of those parameters, usually on
  a real image rather than a drawn diagram
- a **code panel** at the bottom that prints the OpenCV call the current
  controls stand for, so the bridge to the notebook is always on screen
- a **footer** with the four or five things worth saying about the idea

Pages respect the browser's light and dark preference.
