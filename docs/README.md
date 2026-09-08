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

## Hosting them

The folder is static, so GitHub Pages serves it as is. Enable Pages on the
repository, then the demos live at:

```
https://<user>.github.io/<repo>/Interactive%20Visualizations/
```

Because the folder name has a space in it, some tools prefer it renamed to
`interactive-visualizations`. Nothing inside the pages depends on the folder
name; the links between them are all relative.

## What is in a page

Every demo follows the same shape:

- a **control rail** on the left, holding the parameters the lecture asks about
- a **stage** in the middle showing the effect of those parameters, usually on
  a real image rather than a drawn diagram
- a **code panel** at the bottom that prints the OpenCV call the current
  controls stand for, so the bridge to the notebook is always on screen
- a **footer** with the four or five things worth saying about the idea

Pages respect the browser's light and dark preference.

## About the numbers

Where a page reports a count, a coordinate or a threshold, that value was
checked against the same call in OpenCV 4.10 running on the same input, rather
than against the page's own arithmetic. Cross-checking this way is what caught
several real semantic differences during development, for example that
`cv.medianBlur` only ever uses `BORDER_REPLICATE`, that `cv.erode` treats the
outside of the image as maximum rather than zero, and that `cv.filter2D`
rejects `BORDER_WRAP` outright, and that the appendix's own
`bilinear_interpolation` returns zero whenever the requested coordinate is an
exact integer, because it uses `np.ceil(x)` where it means `floor(x) + 1`.

The Lecture 03 video pages use frames decoded from `Illinois_highway.mp4`, the
clip the motion detection notebook opens, downscaled to 320 by 180 and embedded
in the page. The Lecture 05 pages use the church photograph the gradients
notebook opens, downscaled to 448 by 331, and the photograph the Lecture 05
slides themselves show, at its original 320 by 240.

Two of the Lecture 05 pages reimplement non-maxima suppression and hysteresis
rather than calling `cv.Canny`, because that is what the deck and the notebook
teach. Where they differ from the library the page says so and gives the
measured size of the difference: at the settings the pipeline page opens with,
the two agree on 91.8 percent of `cv.Canny`'s edge pixels.

## Editing

Open the file, change the number, reload. The state of a demo lives in a single
`S` object near the top of its script, and the defaults are the values the
lecture uses.

The shared stylesheet and JavaScript helpers the pages were assembled from are
kept in [`_build/`](_build/), for writing new pages rather than for running the
existing ones.
