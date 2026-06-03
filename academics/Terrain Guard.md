# what to do for the hackathon

This is a fantastic problem statement. It looks like a Honeywell Aerospace challenge for a hackathon (Design-A-Thon), and it actually aligns perfectly with the 3D terrain mapping concepts we have been discussing!

The core goal here is to prevent **CFIT (Controlled Flight Into Terrain)**—which is when a perfectly functioning aircraft is accidentally flown into the ground, a mountain, or water, usually due to poor visibility or lack of pilot situational awareness.

To solve this, you need to upgrade from just _visualizing_ the terrain (what we did earlier) to actually _analyzing_ it and assigning a "danger" or "complexity" score to every coordinate.

Here is your step-by-step roadmap to fulfill the requirements of this challenge.

### Phase 1: Data Acquisition (The Foundation)

You need to move away from simple CSVs and start working with standard geospatial raster files (like `.tif` / GeoTIFF).

- **Action:** Go to the OpenTopography API or USGS EarthExplorer.
    
- **Action:** Download a chunk of **SRTM 30m** or **Copernicus GLO-30 DEM** data for a highly mountainous region (like the Himalayas or the Alps) to test your system.
    

### Phase 2: TTCI Computation Pipeline (Deliverable 1)

They want a Python script (using libraries like `rasterio` or `GDAL`) that reads the DEM and calculates a **Terrain Topography Complexity Index (TTCI)**. Since TTCI isn't a single universal standard, you need to derive it by mathematically combining a few factors:

- **Slope:** How steep is the terrain? (Calculated using the elevation difference between neighboring pixels).
    
- **Terrain Ruggedness Index (TRI):** The amount of elevation difference between a grid cell and its 8 surrounding neighbors.
    
- **Elevation:** Absolute height above sea level.
    
- **Action:** Write a pipeline that takes the raw DEM, calculates these parameters, normalizes them, and outputs a new 2D grid where each pixel has a TTCI score (e.g., from 0 = flat/safe to 100 = jagged/dangerous).
    

### Phase 3: Interactive Risk Map (Deliverable 2)

Instead of just a 3D visualizer, they want an interactive 2D web map that highlights the "danger zones."

- **Action:** Use Python libraries like **Folium** or **Leaflet.js** (if you want to build a web dashboard) to render your new TTCI map.
    
- **Visuals:** Color-code it. Safe/flat areas should be transparent or green, while high TTCI (complex/rugged) areas should be glowing red.
    

### Phase 4: The Aviation Safety Feature (Deliverable 3)

You must choose _one_ of these three tools to build on top of your TTCI map.

- **Option A: TAWS-style alert overlay:** (Terrain Awareness and Warning System). You simulate a flight path (a line of coordinates with an altitude). If the flight path gets too close to a red (high TTCI) zone, the system triggers a warning.
    
- **Option B: MSA calculator per route sector:** (Minimum Safe Altitude). You divide the map into grid squares. The script finds the highest elevation point in that square, adds a standard safety buffer (e.g., 1,000 or 2,000 feet), and prints the MSA for that sector.
    
- **Option C: UAS corridor risk scorer:** (Unmanned Aerial Systems / Drones). You write a pathfinding algorithm that tries to draw a flight path from Point A to Point B while strictly avoiding high TTCI zones.

---

