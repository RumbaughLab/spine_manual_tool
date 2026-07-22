# Manual Spine & Filopodia Analysis Tool - User Guide

This guide outlines how to use the interactive Python dashboard for manual dendritic spine targeting, barrier painting, and morphological analysis.

---

## 1. Loading Data & Getting Started
* **Input Folder:** Enter or paste the directory path containing your `.tif` (or `.tiff`) image stacks and their corresponding `.swc` skeleton files into the **Input Folder** text box.
* **Load Remaining:** Click the **Load Remaining** button to load the first unanalyzed image stack in the queue. The tool will automatically check for matching `.swc` files to generate the initial dendritic shaft barrier and baseline dendrite intensity.

---

## 2. Navigation & View Controls (Shortcuts)
You can navigate the 3D stack or adjust your view using either the buttons or keyboard shortcuts:
* **Z-Stack Navigation:** Scroll your mouse wheel up or down while hovering over the image plots to move through Z-slices.
* **`A` (Reset View):** Resets the plot zoom and pan back to the original full native dimensions.
* **`F` (Zoom Rect):** Triggers zoom-to-rectangle mode so you can drag a box over an area of interest. Press **`Escape`** to exit.
* **`D` (Pan Image):** Triggers pan/move mode to drag the image around. Press **`Escape`** to exit.

---

## 3. Targeting & Marking Spines / Filopodia
* **Auto-Peak Z Finding:** Click anywhere on either the **Z-Slice Navigator** or the **Global MIP** plot. The tool automatically scans a $10 \times 10$ pixel spatial box across the entire Z-stack to find the local intensity maximum and locks the target coordinates to that peak.
* **`Z` (Save Spine):** Saves the currently marked point as a quantified **Spine** (marked in red).
* **`X` (Save Filo):** Saves the currently marked point as a **Filopodia** (marked in blue, stored in the table as unquantified).
* **Undo Last (`U`):** Removes the most recently added target from your queue.

---

## 4. Barrier Painting & Adjustment
* **Modes:** Use the **Mode** radio buttons to switch between targeting spines, painting custom barrier regions, or erasing barriers using the **Brush Size** slider and **Clear Paint** button.
* **Sliders:** Fine-tune the visualization and segmentation behavior using the **Win/Lvl** contrast slider, **Barrier µm** thickness slider, **Tolerance** threshold slider, and **Z-Search** range.

---

## 5. Exporting Analysis
* **Analyze All Targets:** Click this button to run batch processing across all saved targets in your queue. It calculates volumes, max intensities, integrated densities, and records all active parameters (barrier thickness, tolerance, and search range) along with the initial dendrite intensity baseline. 
* **Output Files:** Results are automatically saved into an `output_analysis` subfolder within your input directory containing:
  * A `.csv` results summary file.
  * A filtered stack `.tif`.
  * A segmentation mask `.tif`.


---

## Usage
* **flag all the filopodia firs
* **flag all the spine first
* **modify some of the criteria