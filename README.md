# **Team Report**

**Yuting Zhao - CID：06059901**

**Xinyue Liu  - CID：06060204**

**Yinuo Pang - CID：06060377**

**1. What We Have Achieved**

We built Artify, a MATLAB application that converts photographs into artistic renditions. The application supports seven artistic styles, each with adjustable parameters:

**Poster / Pop Art** — Flat colours, high contrast, bold outlines. Key techniques: Mean-Shift colour quantisation, contrast stretching, Sobel edges.

**Cartoon** — Clean regions, comic-like edges. Key techniques: 5D Mean-Shift segmentation, morphological opening, LoG edges.

**Sketch** — Pencil-style line drawing. Key techniques: Mean-Shift quantisation, Canny edge detection.

**Watercolor** — Pigment-like wash, paper texture. Key techniques: Cartoon abstraction, morphological closing, edge darkening.

**Bright Watercolor **— Lighter, more vibrant wash. Similar pipeline with different parameter tuning.

**Oil Painting** — Painterly, colour-block effect. Key techniques: Watershed segmentation, median filtering.

**Stained Glass** — Mosaic-style, jewel tones, lead lines. Key techniques: k-means segmentation, optional Gothic-arch frame.

The application is launched via artify_app, which provides a modern GUI with style dropdown, per-style parameter tuning, before/after slider comparison, SSIM evaluation, and save functionality. Shared modules include meanShiftColorQuant.m and meanShiftSegmentation.m, used across multiple styles for coherent architecture.

**2. How to Run the Application**

**Requirements:**



* MATLAB R2016a or later
* MATLAB Image Processing Toolbox (for edge, strel, watershed, etc.)
* No additional hardware required

**Steps:**



1. Open MATLAB and navigate to the *matlab* folder: \
 cd matlab
2. Download Artify-Project.zip and TestPics.zip from the *whitejack2331703470-cmd GitHub repository*.
3. Extract the downloaded files.
4. Run the application: \
 artify_app
5. Click Load Image and select a file from the `TestPics` folder or any personal image in supported formats (JPG, PNG, BMP, or TIFF).
6. Choose a style from the dropdown menu.
7. Adjust parameters as needed (hints indicate valid ranges).
8. Click “Process” to generate the result.
9. Drag the slider to compare the processed image with the original.
10. Click “Save Result” to export the output.

## 3. Evidence That the Application Works
GUI with loaded image and processed result — Show the main Artify window with an image loaded and one style applied, with the before/after slider visible.
图1
Parameter tuning — Same style with different parameter values to show the effect of adjustments.
图2 图3
canvas — Example of Stained Glass style with the optional mosaic frame enabled.
图4 图5
3. Multiple styles comparison — Same photo processed with style example side by side.
Original figure
图6
Photo for watercolor, cartoon and sketch
图7
Photo for pop art and oil painting
图8
Photo for stained glass
Cartoon:
图9
Bright watercolor:
图10
Watercolor: 
图11
Sketch:
图12
Oil painting:
图13
Pop art:
图14
Stained Glass:
图15






