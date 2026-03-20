# **Personal Statement：**

**Xinyue Liu: see attachment**

# **Logbook：**
**Xinyue Liu: see attachment**
# **Team Report**
https://docs.google.com/document/d/13sOqXAmagMoWpW01OziKeG4sQ64n9WEprG6_-J8Ci_E/edit?usp=sharing

**Yuting Zhao - CID：06059901**

**Xinyue Liu  - CID：06060204**

**Yinuo Pang - CID：06060377**

## **1. What We Have Achieved**

We built Artify, a MATLAB application that converts photographs into artistic renditions. The application supports seven artistic styles, each with adjustable parameters:

**Poster / Pop Art** — Flat colours, high contrast, bold outlines. Key techniques: Mean-Shift colour quantisation, contrast stretching, Sobel edges.

**Cartoon** — Clean regions, comic-like edges. Key techniques: 5D Mean-Shift segmentation, morphological opening, LoG edges.

**Sketch** — Pencil-style line drawing. Key techniques: Mean-Shift quantisation, Canny edge detection.

**Watercolor** — Pigment-like wash, paper texture. Key techniques: Cartoon abstraction, morphological closing, edge darkening.

**Bright Watercolor**— Lighter, more vibrant wash. Similar pipeline with different parameter tuning.

**Oil Painting** — Painterly, colour-block effect. Key techniques: Watershed segmentation, median filtering.

**Stained Glass** — Mosaic-style, jewel tones, lead lines. Key techniques: k-means segmentation, optional Gothic-arch frame.

The application is launched via artify_app, which provides a modern GUI with style dropdown, per-style parameter tuning, before/after slider comparison, SSIM evaluation, and save functionality. Shared modules include meanShiftColorQuant.m and meanShiftSegmentation.m, used across multiple styles for coherent architecture.

## **2. How to Run the Application**

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

## **3. Evidence That the Application Works**

GUI with loaded image and processed result — Show the main Artify window with an image loaded and one style applied, with the before/after slider visible.

<img width="1999" height="1359" alt="Image" src="https://github.com/user-attachments/assets/bb219a70-27d4-4ee1-bbeb-b9189ce82fe2" />




**1. Parameter tuning — Same style with different parameter values to show the effect of adjustments.**

<img width="1065" height="437" alt="Image" src="https://github.com/user-attachments/assets/8adb3aae-2144-4f9a-8265-83118341ea15" />


<img width="966" height="399" alt="Image" src="https://github.com/user-attachments/assets/97dc3233-3d39-4cb3-8f16-d300f9752f21" />




**2. canvas — Example of Stained Glass style with the optional mosaic frame enabled.**


<img width="1999" height="1349" alt="Image" src="https://github.com/user-attachments/assets/ffee0230-8642-4414-b7fa-c752fa34ecb7" />



**3. Multiple styles comparison — Same photo processed with style example side by side.**

**Original figure**


    

<img width="735" height="490" alt="Image" src="https://github.com/user-attachments/assets/74ced792-925f-4717-b474-6855cb183b73" />


**Photo for watercolor, cartoon and sketch**


    

<img width="962" height="612" alt="Image" src="https://github.com/user-attachments/assets/bb3c002c-4fba-4f09-9566-b9441a39bdd7" />



**Photo for pop art and oil painting**


    

<img width="597" height="900" alt="Image" src="https://github.com/user-attachments/assets/c4fcea3b-9c6e-4d98-93e8-e9aed9cab80f" />



**Photo for stained glass**

**Cartoon:**



<img width="1241" height="750" alt="Image" src="https://github.com/user-attachments/assets/2c65196a-e3b3-416a-9eb1-f1e156fe6b37" />


**Bright watercolor:**



<img width="1241" height="748" alt="Image" src="https://github.com/user-attachments/assets/669bb419-6227-4ef7-a0ba-2a8a85ef5250" />


**Watercolor:**



<img width="1232" height="745" alt="Image" src="https://github.com/user-attachments/assets/2d73005d-15e7-4042-9cad-6df18e06ca70" />


**Sketch:**



<img width="1247" height="733" alt="Image" src="https://github.com/user-attachments/assets/65483f7e-d757-415a-b536-cb3c415734f4" />


**Oil painting:**



<img width="1232" height="760" alt="Image" src="https://github.com/user-attachments/assets/e905a3a1-695b-49a2-9069-e10e1ec8abb8" />


**Pop art:**



<img width="1247" height="756" alt="Image" src="https://github.com/user-attachments/assets/112f272f-6618-4266-a1c4-ae4ff78d1768" />


**Stained Glass:**



<img width="1999" height="1349" alt="Image" src="https://github.com/user-attachments/assets/20990537-3937-41fb-a637-7292d022e071" />


## **4. Evaluation: What Our Project Can and Cannot Do**


**Watershed-Based Method (Liu Xinyue)**

This method simulates the interaction between pigment, water, and paper through multi-stage processing. Using morphological abstraction and median filtering, it simplifies images into spatial regions resembling brushstrokes while preserving overall structure. A pigment density model, combined with Gaussian-blurred noise and gradient masks, helps reproduce organic textures such as wet edges and flow effects. However, the method is sensitive to low-contrast regions, where the Watershed transform can cause over-segmentation. Future improvements include bilateral filtering and saliency-based feature extraction to better balance abstraction and detail preservation.


**Mean-Shift Method (Yinuo Pang)**

This approach demonstrates how Mean-Shift segmentation can generate multiple styles—Poster, Cartoon, and Sketch—through different pipeline designs. The Poster style achieves effective colour simplification but struggles with weak edges in low-contrast images. The Cartoon style produces the most visually convincing results but is computationally expensive and may lose fine details. The Sketch style provides strong abstraction but is sensitive to surface texture, leading to noisy line extraction. Future improvements include replacing Canny with Difference-of-Gaussians and using adaptive thresholding for more stable edge detection.


**K-means Method (Yuting Zhao)**

Compared to the watershed method, the k-means approach produces clearer and more structured results. Colour quantisation simplifies the image into coherent regions, while palette remapping enhances decorative quality. Lead-line extraction further defines shapes, and additional elements such as mosaic backgrounds and frames create a complete stained-glass composition. However, the method is sensitive to parameter selection, particularly the choice of *k*. A high *k* leads to excessive fragmentation, while a low *k* may reduce colour contrast and visual richness. Therefore, balancing segmentation detail and colour contrast remains a key challenge.


**Overall Evaluation**

Across all methods, the project demonstrates that different segmentation techniques offer distinct trade-offs between abstraction, detail preservation, and computational complexity. The watershed method provides a foundational painterly effect but lacks stability, while Mean-Shift enables stylistic diversity at a higher computational cost. The k-means stained glass approach achieves the most coherent and visually appealing results by effectively combining colour simplification, structural enhancement, and artistic composition, although it still requires careful parameter tuning.

## **5. Our Application:**

Strengths:



* Seven distinct artistic styles with different visual outcomes.
* Instant feedback via the slider comparison and parameter hints.
* Quantitative evaluation (SSIM and processing time) for understanding style divergence and performance.
* Flexible input — supports common image formats and handles grayscale by converting to RGB.
* No external dependencies — uses only MATLAB and the Image Processing Toolbox.

Limitations:



* Processing time: Cartoon and other segmentation-heavy styles can take 10–30 seconds on large images due to Mean-Shift complexity.
* Sketch quality: Canny edge detection can pick up texture as well as structure, leading to noisy lines in some images.
* Parameter sensitivity: Some styles require parameter tuning for best results on different image types.
* Stained Glass output size: When "Add canvas" is enabled, the output may have different dimensions than the input.

Possible future improvements:



* Additional edge-detection strategies (e.g. DoG) for cleaner Sketch lines.
* Batch processing of multiple images from a folder.
* Performance optimisation for large images.
* Export of parameter presets for reproducible results.

## **6. Project Structure**

matlab/ artify_app.m — Application entry point 

main.m 

getParameters.m 

meanShiftColorQuant.m — Colour-only Mean-Shift quantisation 

meanShiftSegmentation.m — 5D spatial-colour 

Mean-Shift artify_poster.m — Poster / Pop Art style 

artify_cartoon.m — Cartoon style 

artify_sketch.m — Sketch style 

artify_watercolor.m — Watercolor style 

artify_bright_watercolor.m 

artify_oilpainting.m 

artify_stainedglass.m 

lxy_cartoon.m — Shared cartoon abstraction 

colorspace.m — Colour space utilities 

bfilter2.m — Bilateral filter

## **7. AI Acknowledgement**

I would like to acknowledge the use of AI assistance (Gemini；Claude; Cursor; ChatGPT) in the preparation of this logbook. Specifically, AI was used for the following purposes:

**Code Documentation**: Assisting in generating concise and clear English comments for the MATLAB scripts to ensure readability.

**Language Polishing**: Refining the grammar and phrasing of the written English content to ensure professional communication.

However, all critical insights, reflections, and experimental analyses presented in this logbook are my original thoughts, derived from my direct observations during the lab sessions and my understanding of the module's core principles.
