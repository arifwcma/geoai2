## Project: GeoAI2

A QGIS project (geoai2.qgs) based on Wimmera (Victoria, Australia) demonstrating key features of the GeoAI QGIS plugin (https://opengeoai.org/qgis_plugin/).

CRS: EPSG:7854 (GDA2020 / MGA zone 54)


## Approach

This is NOT about writing custom AI models. We are using the built-in features of the GeoAI QGIS plugin (https://opengeoai.org/qgis_plugin/) to demonstrate GeoAI capabilities on Wimmera data. Custom Python code using the geoai library (https://opengeoai.org/) may come later.

The property layer (data/properties/PROPERTY_VIEW.shp) defines AOIs. The idea is to run GeoAI tasks on a selected property.


## Current QGIS Project Layers

1. ESRI World Imagery basemap (named "Aerial") -- XYZ tile layer
2. Wimmera CMA boundary polygon
3. PROPERTY_VIEW (property boundaries for Wimmera)


## Task List (easy to difficult)

1. Moondream VLM -- caption, query, detect on imagery using natural language (no training needed)
2. Segment Anything (SamGeo) -- interactive segmentation via point/text prompts
3. Tree Segmentation (DeepForest) -- pretrained tree crown detection
4. Water Segmentation (OmniWaterMask) -- automated water body detection
5. Semantic Segmentation -- create training data, train model, run inference (e.g. land cover)
6. Instance Segmentation (Mask R-CNN) -- train and infer individual feature boundaries

Tasks 1-4 use pretrained models (no training). Tasks 5-6 involve model training.


## Progress

Task 1 (Moondream VLM): IN PROGRESS
- GeoAI plugin installed in QGIS
- Dependencies installed via built-in installer
- Moondream model loaded
- "Aerial" basemap selected as input raster
- Next step: set mode to Caption and click Run, then try Query and Detect modes


## Git Setup

- Repo: git@github-wcma:arifwcma/geoai2.git (uses SSH alias github-wcma)
- SSH config at ~/.ssh/config routes github-wcma host to a dedicated key (~/.ssh/id_ed25519_wcma)
- The default github.com host maps to the arf-themascoteers account
- sensitive_resources/ was removed from git history and is in .gitignore


## Key Decisions Made

1. We use the GeoAI QGIS plugin features, not custom AI code (for now)
2. Task order follows easy-to-difficult for non-tech colleague demos
3. Property layer used to define AOIs for each task
4. One step at a time -- Arif prefers incremental instructions, not big dumps
