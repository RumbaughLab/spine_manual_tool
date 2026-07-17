# Spine Manual Tool

## Overview
This repository contains a Jupyter Notebook and associated tools for volumetric spine quantification from z-stack images. It was developed to benchmark automated solutions against ground truth data, as existing tools were not optimal for our datasets. 

The application enables the easy extraction of volumes from z-stacks, facilitating manual annotation and improving data traceability.

## Features & Rationale
To facilitate analysis, we implemented an additional processing pipeline designed to:
- **Improve data traceability.**
- **Enable automated processing and batching** of segments to be used with tools like RESPAN.
- **Facilitate manual annotation** by rapidly loading isolated segments one after the other.

## Workflow

### 1. Pre-Processing & ROI Extraction
This step speeds up the workflow by isolating segments before tracing.
1. Open a **z-max projection** of your z-stack. This is significantly faster to load than a full z-stack and makes it much easier to identify branches of interest.
2. Draw Regions of Interest (ROIs) on the z-projection.
3. Run the automated extraction tool. *(Note: Loading the full image—e.g., 500 z-steps—takes about 1 minute, but this process runs entirely automatically).*
4. The tool will automatically extract and crop all ROIs in X, Y, and Z dimensions.

### 2. Tracing and Masking
Once the ROIs are cropped and extracted, loading them for labeling is extremely fast.
1. Load the extracted ROI segments.
2. Trace the neurite using **SNT (Simple Neurite Tracer)**.
3. **Important Calibration**: Ensure the image is properly calibrated to the correct pixel/μm dimensions before tracing. 
4. **Diameter Masking**: While tracing the neurite, use the scroll wheel to adjust and capture the *actual diameter* of the dendrite. This trace acts as a mask barrier during z-quantification.
5. Save the completed trace as an `.swc` file.

### 3. Volumetric Quantification
1. Run the Jupyter Notebook provided in this repository.
2. The notebook uses the `.swc` traces and cropped image data to extract and quantify the 3D spine volumes.

## Examples
Example demonstration videos are available directly in this repository.

## Future Improvements
There are numerous opportunities for further development, including expanding this framework into simpler, fully automated tools based on this manual ground-truth extraction pipeline.

## Contributors
- Maria
- Emilie
- Thomas Vaissiere
