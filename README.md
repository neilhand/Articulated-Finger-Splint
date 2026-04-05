# Articulated Finger Splint

> A 3D-printable articulated finger splint designed to support and protect injured fingers while preserving range of motion.

This repository contains a collection of files to support the paper "3D Printed Hinged Splint For Instability of PIP" authored by Robert White and Neil Hand.

These files are being made available to allow to allow others with better CAD capabilities (this was created by a hand therapist and an electrical enginneer with limitied CAD experience) to itterate on the design, with the ultimate aim that they can create a paratamtizable design that can be easily customized for individual patients.

These files are being made available under the CC BY 4.0 license, to allow you to freely develop and modify the design for personal or commercial use, provided you attribute the original work and authors. 

![V4 Final - Print in Place](V4%20-%20Final%20-%20Print%20in%20place%20v3.png)

---

## Table of Contents

- [Overview](#overview)
- [Design Versions](#design-versions)
- [File Reference](#file-reference)
- [Requirements](#requirements)
- [Printing Instructions](#printing-instructions)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This project provides two final splint designs optimized for FDM 3D printing:

- **V4 – Print in Place**: A single-part design with a built-in articulating hinge. No assembly required — print and wear. This version can be printed on a consumer resin printer, or preferably using a SLS or binder jet printer.
- **V5 – Multipart Print**: A two-part shell with separate connector plates. this is designed for consumer FDM printing with standard filiments. The parts are seperated to allow for printing in the orientation that provides the best strength for the parts (more info later in this doc)

Both final designs have utilised a 3D mesh scan of the injured finger to create a custom fit.

Additonal design itterations that are discussed in the paper are also included to show the evolution of the project

> ⚠️ **Medical Disclaimer**: This splint is a personal/hobbyist project and is not a certified medical device. Consult a medical professional before use for injury treatment.

---

## Design Versions

The project evolved through six iterations. Each version addressed limitations of the previous one.

| Version | Name | Description |
|---------|------|-------------|
| V0 | Multipart Box Test | Proof-of-concept for multi-part joining mechanism |
| V1 | Initial Prototype | Two-ring design with a basic external hinge |
| V2 | Fitted to Finger | Anatomically contoured inner surface based on finger mesh scan added |
| V3 | Enclosed Hinge | Hinge moved inside the body for comfoty and durability |
| V4 | Final – Print in Place | Single-piece articulated design |
| V5 | Final – Multipart Print | Multi-part shell with plates |

### V4 – Print in Place
![V4](V4%20-%20Final%20-%20Print%20in%20place%20v3.png)

### V5 – Multipart Print
![V5](V5%20-%20Final%20-%20Multpart%20Print%20v8.png)

---

## File Reference

```
Articulated-Finger-Splint/
│
├── V0 - Multipart-box-test.*       # Join mechanism prototype
├── V1 - Initial Prototype.*        # First full splint prototype
├── V2 - Fitted to Finger.*         # Anatomical fit iteration
├── V3 - Enclosed Hinge.*           # Enclosed hinge iteration
├── V4 - Final - Print in place.*   # ✅ Recommended: single-piece print
├── V5 - Final - Multpart Print.*   # ✅ Recommended: multi-part print
│
├── FingerMesh.stl                  # Reference mesh of a finger for fitting
│
└── 3DModel finger/                 # Reference finger scan
    ├── OBJ/                        # OBJ format (with materials)
    └── USDZ/                       # USDZ format (AR preview on iPhone/iPad)
```

Each version includes three file types:

| Extension | Format | Use |
|-----------|--------|-----|
| `.f3d` | Fusion 360 | Full parametric source file for editing |
| `.step` | STEP / AP214 | CAD interchange (FreeCAD, SolidWorks, etc.) |
| `.png` | Image | Design preview |

---

## Design Process and Fitting

This design creates a structure that limits lateral movment using two pivot points that are positioned to allow flexion and extension while restricting side-to-side movement. These pivots do not need to handle much direct force since when one is in compression the other is in extension, spreading the forces. As such, they can be relatively simple and lightweight.

The most important part of the design was identifying the correct placement of the dual pivot points on the splint to ensure proper articulation and comfort. This was achived through multiple iterations and prototypes across multiple versions of the design.

It bagan with marking the injured fingers with a sharpie at the desired location, an image of the finger including the placement was then important into CAD and used as the initial reference for the pivots. Subsequent iterations were then made to adjust the placement of the pivots to ensure proper articulation. You will find some of these images in the f3d files as canvases.

Early versions of the design used a rough appoximation of the injured finger based on the previously mentioned images. This was effective, but resulting in sharper edges and presure points. This was initially addressed by adding a soft layer of material to the splint, but this was fiddly and not ideal for long term use. The final design addresses this by using a detailed scan of the finger and subtracting that mesh from the final design for a perfect fit.

For this project the mesh was created by creating a plaster cast of the finger and then scanning it using an iPhone app meant for photogrammetry (generating a 3D model from multiple images or video). This was chosen rather than a direct finger scan as keeping the finger still for an extended period of time was not possible. This could be address using a structured light scanner or other similar technology, which could scan more accurately and quickly. If the spint is only needed for a short period of time, the approximation could be used.

## Requirements

### Software
- [Autodesk Fusion 360](https://www.autodesk.com/products/fusion-360) (to edit `.f3d` source files)
- Any CAD tool supporting STEP files (FreeCAD, SolidWorks, Onshape, etc.) for `.step` files
- A slicer such as [Bambu Studio](https://bambulab.com/en/download/studio), [PrusaSlicer](https://www.prusa3d.com/page/prusaslicer_424/), or [Ultimaker Cura](https://ultimaker.com/software/ultimaker-cura/)

### Hardware
- **V4**: Resin, SLS, binderjet printing or similer technology. This can be done at home or through a service provider such as PCBWay in the case of the Nylon version that has been used extensively.
- **V5**: FDM printer with a preffered nozzle diameter of 0.4mm. 

### Materials
| Material | Notes |
|----------|-------|
| **PLA** | Rigid; easy to print but brittle |
| **PETG** | Good balance of printability and durability |

---

## Printing Instructions

### V4 – Print in Place (Single Part)

> This was pinted on both a consumer grade resign printer as well as a industrial  binderjet printer (PCBway. Another vendor was also used, but the quality was sub par and the parts were either two fragile or did not articulate).

The part is orientated such that the hinge is printed in the open/extended position and parallel to the print plane regardless of printing process. This mazimizes the chance of successful printing and articulation.

The choice of resin seems to be very important and the more opaque the resin the higher the chance of success. The print must be removed from support material and cleaned thoroughly to ensure proper articulation prior to UV curing.

>**A note on failure modes and chice of resin or printing technology**  
The resin used for the prototyping was a standard gray 8K photopolymer resin. This resulted in a good part and high success rate, but there wer concerns about the sudden snap of the parts under stress. The Nylon printed parts have shown to be more durable and less prone to sudden failure as the deform rather than snap.


### V5 – Multipart Print
> This was designed to be printed on a consumer grade FDM printer.
The hing parts are printed flat to ensure maximum strength and minimize warping. The front and back finger parts were printed at a 45 degree angle to decrease the chance of breakage across a layer line. The supports were placed on the back of the parts to ensure good surface finish where the splint contacts the skin.

The hinges are held in place using a small piece of 1.75mm PLA filament that is inserted into the hinge and then the end melted smooth with the surface using a soldering iron or similar tool.

This multipart design was created to allow for easier printing and assembly especially in a clinical environment. The parts are small and can be printed quickly, it is also possible a mixed collection of part can be mixed and matched to create a close enough fit for many without neededing special design and finger scanning

---

## Customization

There is no customization available at this time and the `.f3d` source files are provided to show how the parts were designed and allow for modification and evolution hopefully towards a fully parametic design.

---

## Contributing

Contributions, improvements, and remixes are welcome!

1. Fork this repository.
2. Create a feature branch: `git checkout -b feature/my-improvement`
3. Commit your changes: `git commit -m 'Add my improvement'`
4. Push to the branch: `git push origin feature/my-improvement`
5. Open a Pull Request.


---

## License

This project is licensed under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license — you are free to share and adapt the design for any purpose, provided appropriate credit is given.

---
