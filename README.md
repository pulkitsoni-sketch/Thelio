# Thelio Parts Reconstruction & Validation

Methodology
Original parts were imported into Fusion.
Data for edges, arcs, and lines were extracted to create profiles.
These profiles were added or subtracted to generate the final 3D part designs.

Validation
A validation script (validate.py) compares the rebuilt output models to the original parts using cadquery and trimesh. It calculates Volumetric Difference (mm³ and %) and Symmetric Difference (mm³ and %).
Validation Output: 

╔══════════════════════════════════════════════════════════════════════════════╗
║  Thelio Parts — Validation Report (Volume & Symmetric Difference)           ║
╚══════════════════════════════════════════════════════════════════════════════╝
  Originals   : /Users/softage/Desktop/Thelio/Original
  Outputs     : /Users/softage/Desktop/Thelio
  STEP loader : cadquery
  trimesh     : ✓

  [OK                                      ] PN-000641 v10
  [OK                                      ] PN-000643 v36
  [OK                                      ] PN-000644 v54
  [OK                                      ] PN-000645 v63
  [OK                                      ] PN-000646 v10
  [OK                                      ] PN-000647 v22
  [OK                                      ] PN-000648 v17
  [OK                                      ] PN-000650 v12
  [OK                                      ] PN-000651 v13
  [OK                                      ] PN-000652 v17

┌──────────────────────────────────────────────────────────────────────────────┐
│  Part Name               Vol Diff (mm³)     Vol (%)    Sym Diff (mm³)     Sym (%)  │
├──────────────────────────────────────────────────────────────────────────────┤
│  PN-000641 v10                    0.016        0.00%             0.018        0.00%  │
│  PN-000643 v36                   49.135        0.03%            49.541        0.03%  │
│  PN-000644 v54                   24.244        0.02%            24.363        0.02%  │
│  PN-000645 v63                   97.207        0.06%            97.463        0.06%  │
│  PN-000646 v10                   14.597        0.01%            15.844        0.01%  │
│  PN-000647 v22                    0.010        0.00%             0.010        0.00%  │
│  PN-000648 v17                    0.727        0.00%             1.699        0.00%  │
│  PN-000650 v12                    7.065        0.00%            32.887        0.01%  │
│  PN-000651 v13                    0.001        0.00%             0.001        0.00%  │
│  PN-000652 v17                    0.528        0.00%                 —           —  │
└──────────────────────────────────────────────────────────────────────────────┘

  Summary : 10/10 parts processed, 0 skipped

  Notes:
  • Vol Diff  = |volume(original) − volume(output)|  in mm³
  • Vol (%)   = Vol Diff as % of original volume
  • Sym Diff  = (A−B) ∪ (B−A) boolean volume in mm³  [requires watertight meshes]
  • Sym (%)   = Sym Diff as % of original volume
  • '—' in Sym columns = open-shell mesh or trimesh unavailable

Time Taken: 18 hours 
