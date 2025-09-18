# Calculator Project

This is a simple calculator web application for generating fluid type scale (clamp) CSS values based on pixel and viewport ranges.

## How the Calculator Works

1. **Inputs:**
	- **Min value (px):** The smallest font size (in pixels) for the smallest viewport.
	- **Max value (px):** The largest font size (in pixels) for the largest viewport. (Can be auto-calculated)
	- **Min viewport (px):** The viewport width at which the min value applies.
	- **Max viewport (px):** The viewport width at which the max value applies.
	- **Auto-calc max:** Optionally, the max value can be calculated automatically based on the ratio of min value and viewport sizes.

+2. **Live Calculation:**
	 - As you change any input, the calculator instantly updates the results and preview.
	 - The calculator computes the equivalent `vw` values for the min and max font sizes, then generates a fluid CSS formula using `calc()` and `clamp()`.

2. **Live Calculation:**
	 **Formulas Used:**

	 - **Convert px to vw:**
		 \[
		 	ext{vw value} = \frac{\text{px value}}{\text{viewport width}} \times 100
		 \]

	 - **Fluid formula:**
		 \[
		 	ext{fluid} = \text{minVW} + (\text{maxVW} - \text{minVW}) \times \frac{(100vw - \text{minViewport}px)}{\text{maxViewport} - \text{minViewport}}
		 \]

	 - **Clamp formula:**
		 \[
		 	ext{clamp}(\text{minVW}, \text{fluid}, \text{maxVW})
		 \]

3. **Output:**
	- The result section shows the conversion from px to vw for both min and max values, the fluid formula, and the clamp formula.
	- A CSS code block is provided for easy copy-paste into your stylesheet.
	 - **Auto-calculate max value (when enabled):**
		 \[
		 	ext{maxPx} = \frac{\text{minViewport}}{\text{maxViewport}} \times \text{minPx}
		 \]
	- The live preview updates the font size in real time as you adjust the inputs or resize the browser window.

## Files
- `index.html`: Main HTML file for the calculator UI and logic.

## Usage
Open `index.html` in your browser to use the calculator.

## License
MIT License
