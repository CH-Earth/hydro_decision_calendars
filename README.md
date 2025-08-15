# Decision Calendar

A Python-based tool for creating Decision Calendar Plots for Hydrological Forecasting.

## Overview

This repository contains tools to generate decision calendar visualizations for hydrological forecasting. Decision calendars help river forecast centers, water resource managers and stakeholders understand the timing of key decisions and their relationship to hydrological forecasts.

## Repository Structure

- `notebooks/` - Jupyter Notebook for creating decision calendars
-`config/` - Configuration files in YAML format
  - `chena.yaml` - Configuration for Chena River analysis
  - `ross.yaml` - Configuration for Ross River analysis
- `scripts/` - Python scripts for generating decision calendars
  - `decision_calendars.py` - Main script for creating decision calendar plots
- `data/` - Data files for streamflow and snow data
- `output/` - Output files for decision calendars
- `images/` - Images used in the decision calendars

## Example Output

![Example Decision Calendar](./output/alaska_decision_calendars.png)

## Getting Started

### Prerequisites

- Python 3.x
- Required Python packages (recommend creating a virtual environment):
  ```bash
  pip install jupyter numpy pandas matplotlib pyyaml pycirclize
  ```

### Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/CH-Earth/hydro_decision_calendars.git
   cd decision_calendar
   ```

2. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

3. Run the notebook `notebooks/decision_calendars.ipynb` to create decision calendars.

4. Configure your analysis (and colour schemes) by modifying the YAML files in the `config/` directory to match your specific river system and decision points.

## Updating the config files

The YAML configuration files in the `config/` directory define the parameters for each river system's decision calendar. You can use the existing templates (`chena.yaml` and `ross.yaml`) as examples for creating configurations for other river systems.

# Configuration Update Instructions

## **Colors and Styles**
To update colors or styles:  
1. Modify the **hex codes** under each relevant section.  
   - Example: Change `annual_activities.critical_period` from `"#896279"` to `"#123456"`.  
2. Update **styles** (e.g., line types, markers) in the `styles` section:  
   - `linestyle`: Options include `"-"` (solid), `"--"` (dashed), `":"` (dotted), or `"-."` (dashdot).  
   - `linewidth`: Adjust thickness (e.g., `3` for thicker lines).  
   - `marker`: Update to other symbols like `"o"`, `"P"`, or `"v"`.  
   - `markerfacecolor`: Use colors defined in `visualization` or input custom hex codes.

## **Track Configurations**
Track configurations define visualization details like colors, line types, and ranges.  
- **To update specific tracks**:  
   1. Change `type` (e.g., `"line"`, `"infill"`, `"marker"`).  
   2. Update `color` using the keys in the `colors` section or custom hex codes.  
   3. Modify `linestyle`, `linewidth`, and `alpha` (transparency).  
   4. Adjust `r_start`, `r_end`, and `months` to change placement and duration.  
   - Example:  
     ```yaml
     hydrological_critical_period:
       type: "infill"
       color: "hydrological_forecasting.critical_period"
       alpha: 0.7
       r_start: 65
       r_end: 86
       months: ["Apr", "May", "Jun", "Jul", "Aug", "Sep"]
     ```

---

## **Legend Groups**
Legend groups control the labels and descriptions for different elements.  
- **To update**:  
   1. Modify `description` for the group title.  
   2. Adjust the `color` and `linestyle` for clarity.  
   3. Add or remove `elements` as needed:  
      - Use `type` options like `"line"`, `"marker"`, or `"space"`.  
      - Example:  
        ```yaml
        - type: line
          color: "hydrological_forecasting.forecast"
          linestyle: "dotted"
          linewidth: 3
          label: "HEFS Forecasts"
        ```

---

## **Plot Settings**
To update plot configurations:  
1. Modify figure size:  
   - Example: Change `figsize: [30, 16]` to adjust width and height.  
2. Update title text under `titles`.  
3. Adjust the legend position (`loc`) and style attributes like `fontsize` and `edgecolor`.


Contributions are welcome! Please feel free to submit a Pull Request.

