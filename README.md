# NYC Basketball Courts Finder

## About This Project

This is a project I created to help people find basketball courts in New York City. I built it as a fun way to combine web mapping with local sports data, and it’s completely self-contained. The application uses Leaflet to display an interactive map with custom markers, a search bar to filter courts by name or location, and borough filter buttons. For borough filtering, the project loads a NYC borough boundaries GeoJSON file and uses Turf.js to perform point‐in‐polygon calculations, so courts are accurately classified by borough.

## Features

- **Interactive Map:**  
  The map is centered on New York City and uses [Leaflet](https://leafletjs.com/) to load map tiles from OpenStreetMap.

- **Custom Marker Icon:**  
  Each basketball court is marked with a custom icon (`basketball.png`). Clicking on a marker opens a popup displaying the court’s name and location.

- **Search Functionality:**  
  The search bar filters both the list of courts and the map markers, making it easy to find the court you're looking for.

- **Borough Filtering:**  
  You can filter courts by borough using buttons. The project loads a NYC borough boundaries GeoJSON file and uses [Turf.js](https://turfjs.org/) to determine the borough for each court through point-in-polygon checks.

- **Responsive Design:**  
  The design is simple and responsive, ensuring that it works well on both desktop and mobile devices.

## Data Source

The court data is sourced from the [Directory of Basketball Courts](https://data.cityofnewyork.us/Recreation/Directory-of-Basketball-Courts/b937-zdky/about_data) provided by the City of New York. I downloaded the JSON version of this dataset (named `DPR_Basketball_001.json`) and used it as the basis for this project.

Additionally, the project uses a NYC borough boundaries GeoJSON file (named `nyc_borough_boundaries.geojson`) to determine court boroughs via Turf.js.

## File Structure

- **index.html:**  
  The main HTML file that contains the code for the interactive map, search functionality, custom marker configuration, and spatial borough filtering logic.

- **DPR_Basketball_001.json:**  
  A JSON file with data for NYC basketball courts, downloaded from the [Directory of Basketball Courts](https://data.cityofnewyork.us/Recreation/Directory-of-Basketball-Courts/b937-zdky/about_data). Each record includes properties such as `lat` (latitude), `lon` (longitude), `Name`, and `Location`.

- **basketball.png:**  
  The custom image used as the marker icon for the basketball courts.

- **nyc_borough_boundaries.geojson:**  
  A GeoJSON file containing NYC borough boundaries. Turf.js uses this file to determine the borough of each court.

## Installation & Usage

1. **Clone or Download the Repository:**  
   Ensure that the following files are in the same directory:
   - `index.html`
   - `DPR_Basketball_001.json`
   - `basketball.png`
   - `nyc_borough_boundaries.geojson`

2. **Run a Local Web Server:**  
   Since the project uses the `fetch` API to load JSON data, it must be run on a local server rather than opened directly in your browser.

   **Using Node.js and `http-server`:**
   ```bash
   npm install -g http-server
   http-server
