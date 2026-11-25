# 3D SES Viewer

BEE 420/520 Ecological Systems Analysis, Oregon State University.

A single-file web page (`index.html`) that draws the 3D socio-ecological system (SES) of a case study from FEGS Scoping Tool (FST) results:

- X axis: stakeholder groups (FST Figure 3 results), grouped by tier.
- Y axis: beneficiary subcategories (Table 4), grouped by beneficiary category.
- Z axis: environmental attribute subcategories (Table 5), grouped by attribute category.

Each axis runs from 0 to 1; each item takes a slice equal to its share of the FST result. Design alternatives are boxes that span the cut points of their 3 target stakeholder groups, beneficiaries and attributes. The page computes and highlights the overlap box of each pair of alternatives.

## Use

1. In `BEE420_AHP_Tillamook_improved_v3.xlsx`, open sheet `3D_CSV` and save a copy as CSV UTF-8.
2. Open the viewer and click **Upload CSV**. The scene and the form fields fill from the file; edit values and click **Apply to 3D**.
3. Rotate, zoom and pan with the mouse. Hover or click a box or grid cell to see its [min, max] intervals, side lengths and volume.

`tillamook_3d_ses.csv` is the Tillamook River Wetlands example (also built into the page).

CSV columns: `record,axis,group,name,value,min,max,label`. `record` is `axis` (one row per item) or `alt` (one row per alternative and axis X, Y, Z, plus an optional L row for the SES linkage score).

No build step or backend: Three.js and OrbitControls load from jsDelivr.
