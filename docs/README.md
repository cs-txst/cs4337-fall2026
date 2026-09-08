# CS 4337 Interactive Visualizations

Browser demos that accompany the lecture slides and the Jupyter notebooks for CS 4337, Introduction to Computer Vision.

**The demos are online at <https://cs-txst.github.io/cs4337-fall2026/>.** Nothing to download, nothing to install.

Working from a copy of this folder instead, open [`index.html`](index.html) for the same list, organized by lecture. Each lecture has its own folder with its own index.

## Running them

Double-click any `.html` file. That is the whole procedure.

Every page is a single self-contained document, with its CSS, JavaScript and images inlined. There is no build step, no package to install, no server to start and no network request, so the pages work from a USB stick, from a lab machine, or from a laptop with the wifi off. Light and dark browser themes are both supported.

## Conventions

Every page carries a control rail for the parameters the lecture asks about, a stage showing their effect on a real image, a code panel printing the OpenCV call the current controls stand for, and a short footer. Values a page reports are checked against OpenCV itself on the same input, not against the page's own arithmetic. Where a page reimplements an operation rather than calling the library, it says so and gives the measured size of the difference.

To change a demo, open the file and edit the `S` object near the top of its script: those are the defaults the lecture uses. The shared stylesheet and helpers in [`_build/`](_build/) are for writing new pages, not for running existing ones.
