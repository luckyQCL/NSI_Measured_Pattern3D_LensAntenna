MEASURED 3D RADIATION PATTERN EXPLORER

Open Radiation_Pattern_Explorer.html in a desktop browser (Chrome, Edge or Firefox).
No MATLAB, internet connection, package installation or local server is required.
Allow the file a few seconds to load; it contains all 70 states and plotting code.
3D rotation requires browser WebGL support. The 2D cuts, maps, and tables are also available.

Choose frequency (23/23.5/24/24.5/25 GHz), excitation (HP/VP), and port (1-7).
3D surfaces and angular maps use the MATLAB-style 256-color turbo rainbow map.
Tabs provide 3D patterns, 2D cuts, angular maps, all metrics, and processing definitions.
Current-data CSV and metric CSV/LaTeX exports are generated locally by the page.

Processing:
- Input has existing +0.5 dB for VP1-7 and +2 dB for HP1/7, both components.
- These existing offsets are retained, never repeated. Their calibration basis is not
  independently established by the uploaded files.
- An additional +1 dB is added to both components for the SMA-SSMP adapter.
  The 24 GHz estimate is used across 23-25 GHz as a band approximation.
- Measured directions are rotated about Y by [-60,-40,-20,0,20,40,60] degrees.
- Exported polarization basis and phase reference are retained. There is no
  vector-polarization-basis conversion, adapter phase, or phase-origin correction.
- Quantitative calculations use the full 131x131 angular grids.
- No smoothing or extrapolation. Coverage is the measured local +/-65 degree Az/El
  sector after spatial rotation, not the full sphere or an independent validity bound.
- The 15-degree cone yields sidelobe candidates only and can include fan-beam
  main-lobe structure. Verify it before citing an SLL.
- Out-of-plane maximum (|El|>10 degrees) may include part of the fan main beam.

Verification:
For 23/24/25 GHz, co-pol peak, direction, Az HPBW, XPD, and default sidelobe
candidates match the uploaded MATLAB metrics within numerical precision.
All five frequency grids are read directly from the respective Excel columns.
Strict |El|>10 uses integer
grid angles to avoid floating-point inclusion of the +/-10 degree boundary.
Browser UI rendering was not verified in the build environment because the
managed preview service was unavailable. Application logic and all 70 states
were tested with DOM/plot stubs; this is not browser rendering QA.
