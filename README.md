# Building Extraction GEE Tool

Interactive Google Earth Engine app to find, filter, visualize, and export building footprints using the Open Buildings v3 polygon dataset.

## Demo
- Draw an area on the map.
- Set `Min Confidence` and `Min Area (m²)`.
- Click **Extract Buildings** to view results.
- Click **Export to My Drive** to save a Shapefile.

![preview](screenshot.png)

## Features
- Instant ROI drawing in the GEE map.
- Filter by model `confidence` and minimum `area`.
- Clip footprints to ROI and assign unique IDs.
- Visual preview: ROI in red, buildings in green.
- Export results to Google Drive as Shapefile.
- Lightweight, self-contained script for direct paste into the GEE Code Editor.

## Files
- `building_extraction_gee.js` — the full GEE script (paste into GEE).
- `screenshot.png` — example output.
- `LICENSE` — MIT.

## How it works (short)
1. Load `GOOGLE/Research/open-buildings/v3/polygons`.
2. User draws ROI with drawing tools.
3. Script filters by `confidence` and `area`.
4. Polygons clipped to ROI, assigned `UID`.
5. Visualize and export via `Export.table.toDrive()`.

## Paste-and-run (in GEE Code Editor)
1. Create new script in https://code.earthengine.google.com/.  
2. Paste the contents of `building_extraction_gee.js`.  
3. Authorize Earth Engine.  
4. Use **Start Drawing** then **Extract Buildings** then **Export to My Drive**.

## Configurable constants (top of script)
```javascript
var OPEN_BUILDINGS = 'GOOGLE/Research/open-buildings/v3/polygons';
var EXPORT_FOLDER = 'My_Building_Footprints';
var MIN_CONFIDENCE = 0.5;
var MIN_AREA = 6; // in square meters
