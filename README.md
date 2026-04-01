# Contour Plot Bathymetry with Python

This repository contains a simple yet effective Python project that demonstrates how to visualize ocean depth (bathymetry) data using contour plots. 

The project uses data from GEBCO (General Bathymetric Chart of the Oceans) and plots it using standard scientific Python libraries, mapping the land and sea depths intelligently to provide an intuitive visualization.

## Technologies Used
* **Python 3**
* **netCDF4**: For reading and parsing the `.nc` (Network Common Data Form) dataset from GEBCO.
* **Matplotlib**: For plotting the `contour` and `contourf` visualizations.
* **NumPy**: For array manipulation, masking land vs sea data, and creating the meshgrid.
* **Basemap**: (Optional) For advanced geographic projections.

## Project Structure
* `contour_plot.ipynb`: The main Jupyter Notebook that contains all the code to load the NetCDF data, process the coordinates, and plot the map.
* `GEBCO_25_Jan_2026_66ab65223920/`: A directory containing the bathymetry dataset (`gebco_2025_*.nc`) as well as the documentation and terms of use from GEBCO.

## How it Works
1. **Loading Data**: Extracts Longitude (`lon`), Latitude (`lat`), and Elevation (`bathymetry`) data directly from the netCDF file.
2. **Masking Elevation**: Uses NumPy's `where` function to separate sea data (elevation < 0) and land data (elevation > 0) to apply different coloring.
3. **Meshing**: Sets up a coordinate meshgrid for plotting.
4. **Plotting**: Uses Matplotlib to plot the land using the `terrain` colormap with filled contours (`contourf`) and sea level using the `jet` colormap with contour lines (`contour`).

## Running the Code
To run the notebook, install the dependencies via pip:
```bash
pip install netCDF4 basemap matplotlib numpy
```
Open the `contour_plot.ipynb` in Jupyter Notebook or Google Colab and run through the cells. Make sure to update the path to the dataset if it's placed differently.
