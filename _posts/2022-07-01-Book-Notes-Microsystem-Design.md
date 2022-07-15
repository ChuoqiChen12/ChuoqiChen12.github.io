---
title: Microsystem Design -- Part 1 Getting Started
author: Chuoqi Chen
date: 2022-07-01 10:00:00 -0400
categories: [Book Notes, Microsystem Design]
tags: [mems, notes]
math: true
mermaid: true
image:
  path: /commons/devices-mockup.png
  width: 800
  height: 500
  alt: Responsive rendering of Chirpy theme on multiple devices.
---
<!-- <style>body {text-align: justify}</style> -->

This is my study Notes of the book "MICROSYSTEM DESIGN". 

---

**Title:** Microsystem Design  

**Author:** Stephen D. Senturia

**Duration**: *07/2022-present*

---

# Chapter 1 Introduction

> <p align="justify"><i> What's in a name?...A rose by any other name would smell as sweet.</i></p>
> <p align="right"> -- W. Shakespeare in <i>Romeo and Juliet</i><p>

## 1.1 Microsystems vs. MEMS

### 1.1.1 What are they?
<p align="justify">
"Microelectromechnical systems(MEMS)": <b><i>micro</i></b> establishes a dimensional scale, <b><i>electro</i></b> suggests either electricity or electronics(or both), and <b><i>mechanical</i></b> suggests moving parts of some kind. But the concept has gown to encompass many other types of small things including thermal, magnetic. fludic, and optical devices and systems, with or without moving parts.
</p>


In general, MEMS share several common features:
<ul>
<li><p align="justify">MEMS involve both electronic and non-electronic elecments, and perform functions that can include signal acquisition(sensing), signal processing, actuation, display, and control. (performing chemical and biochemical reactions and assays)</p></li>
<li> <p align="justify">System issues including packaging, system partitioning into componens, calibration, signal -to-noise ratio, stability, and reliability must be confronted.</p></li>
<li> <p align="justify">The most successful MEMS have been those which involve paradigm shifts from the "macro" way of doing things. Great examples are inkjet print head, thin-film magnetic disk heads and microfluidic devices.</p></li>
<li> <p align="justify">Some MEMS involve large arrays of microfabricated elements, such as uncooled ingrared imaging devices.</p></li>
</ul>


### 1.1.2 How are they made?
<p align="justify">
"micromachining": Lithographic techiniques require flat susbstrates. Silicon is often used. Lithography offers in-place sub-micron precision on dimension scales from micron and milimeter. Thin-fillm deposition and etching techiniques in combination with wafer-bonding techniques allow patterning of the third dimension. Integrated circuits and partition the microsystem into susbsystems are two ways to build the system. Encapsulation and packaging of the components into a system impact the design too. </p>

### 1.1.3 What are they made of?
<p align="justify">
The choice of materials is determined by microfabrication constraint. Most of these are inorganic materials, including silicon, silicon dioxide, silicon nitride, aluminum and tunsten. Certain polymer might be use as well. </p>

<p align="justify">
Certain properties  are critical in device performance, for examplt, the elastic modulus or residual stress of a suspended beam.</p> 

### 1.1.4 How are they designed? 
<p align="justify">
On one level, the designer mush documen the need and specificaiton for a proposed microsystem. At another level, for each proposed approach, one must deal with details of partitioning the system into components, materials selection and the responding fabrication sequences for each componen, methods for packaging and assembly.</p>

<p align="justify">
Quantitive models play a key role in the design process.(perdiction, troubleshooting, evalution)</p>

## 1.2 Markets for Microsystems and MEMS
> *Forecasting is difficult. expecially the future.*
> <p align="right"> <i> -- Chinese forture cookies</i></p>

## 1.3 Case Studies

| **Case Study**                   | **Partitioning** | **Technology**                                                           | **Transduction**                                                      | **Packaging**                                         |
|----------------------------------|------------------|--------------------------------------------------------------------------|-----------------------------------------------------------------------|-------------------------------------------------------|
| Pressure Sensor                  | Monolithic       | Bulk micromachining with bipolar circuitry plus glass frit wafer bongnig | Piezoresistive sensing of diaphram deflection                         | Plastic                                               |
| Accelerometer                    | Monolithic       | Surface micromachining with CMOS circuitry                               | Capacitive detection of proofmass motion                              | Metal can                                             |
| Resonant Rate Gyroscope          | Hybrid           | Bulk micromachined quatz                                                 | Piezoelectric sensing of rotation-induced excitation of resonant mode | Metal can                                             |
| Electrostatically Driven Display | Hybrid           | Surface micromachining using XeF2 release                                | Electrostatic actuation of suspended tensile ribbons                  | Bonded glass device cap plus direct wire bond to ASIC |
| DNA Amplification with PCR       | Hybrid           | Bongded etched glass                                                     | Pressure-driven flow across temperature-controlled zones              | Microcapillaries attached with adhesive               |
| Catalytic Combustible Gas Sensor | Hybrid           | Surface micromachined with selective deposition of catalyst              | Resistance change due to heat of reaction of combustible gas          | Custom mounting for research use                      |

<p align = "center">
Table 1.2 Summary of the Case Studies examined in this book
</p>

---

# Chapter 2 An Approach To MEMS Design
> <p align="justify"><i>If technology-driven design is a hammer looking for a nail, then markei-driven design is a nail looking for a hammer. A good designer will match hammers to nails, regardless of which comes first.</i> 
> <p align="right"> - Anonymous </p>

## 2.1 Design: The Big Picture
<p align="justify">
Examine the big picture, including difficult subhects such as creativity and invention, market opportunities, and choices of technologies, system architectures, and manufacturing methods.
</p>

### 2.1.1 Device Categories
<ul>
<li><p align="justify"><b>Technology Demonstrations:</b> small numbers of working devices are needed to test a device concept or push the capabilities and limits of a particular fabrication technology.(require only a handful of working devices. Device-todevice consistency is not usually important.)</p></li>
<li><p align="justify"><b>Research Tools:</b> components or fully systems have the porpose of performing a highly specialized task. (must typically be calibrated, and should have repeatable behavior.)</p></li>
<li><p align="justify"><b>Commercial Products:</b>The numbers of working devices and the degree of precision and accuracy needed depend on the market.(Device-todevice consistency and high manufacturing yield are likely to be of paramount importance.)</p></li>
</ul>

### 2.1.2 High-Level Design Issues
- **Market:** need? How large is the market? How fast will it develop?
- **Impact:** Paradigm shifts?
- **Competition:** Equivalent product
- **Technology:** Make and package the product available in-house or must be acquired through vendor?
- **Manufacturing:** acceptable cost

Different product has different priority.

|     **Category**       |**Markets**|**Impact**|**Competition**|**Technology**|**Manufacturing**|
|------------------------|-----------|----------|---------------|--------------|-----------------|
|Technology Demonstration|           |    ++    |               |      +++     |                 |
|Research Tools          |    ++     |    ++    |      +        |      +++     |        ++       | 
| Commercial Products    |    +++    |    +++   |     +++       |      +++     |        +++      |

<p align = "center">
Table 2.1 Relative Importance of High-Level Design Issues
</p>

## 2.2 Modeling Levels

<p align = "center">
<img src = "/assets/img/post/2022-07-01-notes-microsystem/2.2_modeling_levels.png">
</p>
<p align = "center">
Fig.2.2 - Different modelings levels for microsystems. 
</p>

<p align="justify">
At the top is the <i>system level</i>. A coupled set of ordinary differential equations (ODE's) to describe the dynamical behavior of the system(block-diagram descriptions and lumped-element circuit models), often written in  a coupled set of first-order ordinary differential equations for the state variables of the system. </p>

<p align="justify">
At the bottom is the <i>process level</i>. This is where the process sequence and photomask designs for device manufacture are created. (CAD & TCAD)</p>

<p align="justify">
The <i>physical level</i> addresses the behavior of real devices in the threedimensional continuum. The governing equations are typically partial differential equations (PDE's). </p>

<p align="justify">
At <i>device level</i>, create what are called macro-models or reduced-order models in a form that captures the essential physical behavior of a component of the system, and simultaneously is directly compatible with a system-level description.</p>

### 2.2.1 Analytical or Numerical?
- **SIMULINK** for system-level modeling
- **MATLAB** for selected numerical device-level and physical-level simulation

Important block diagram can be referred.

<p align = "center">
<img src = "/assets/img/post/2022-07-01-notes-microsystem/2.3 Expanded view of the Modeling and Anlysis block.png">
</p>
<p align = "center">
Fig.2.3 - Expanded view of the "Modeling and Analysis" block.
</p>

## 2.4 Going Forward From Here
<p align="justify">
Developing the analysis tools to assist in (1) the assessment of different device designs and their relative performance and (2) the prediction of performance (in great detail) for the design ultimately selected. The following issues are concerned: </p>

- **System Architecture:** microfabricaed components, electronics and the package
- **System Partitioning:** how affect packaging?
- **Transduction Methods:** variations that would improve performance or reduce cost
- **Domain-Specific Knowledge:** devices typically involve at least two energy domains(laws of physics and chemitry)
- **Electronics:** Interface between physical device and electronic part of the system; device noise

---

# Chapter 3 Introduction
> In small Propoertions we just beauties see;
>
> And in short measures, life may perfect be 
> <p align="right"> -- Ben Jonson </p>

## 3.2 Wafer-level Processes
### 3.2.1 Substrates
<p align="justify">
Planar substrates of choice include single-crystal silicon, single-crystal quartz, glass, and fused (amorphous) quartz. [200 mm (8") dimater wafers are now standard, with 300 mm (12") diamter coming next] Careful planning and a well-designed product mix are required to make costeffective use of the production capacity of MEMS fabrication facilities.</p>

#### 3.2.1.1 Silicon Wafers
<p align="justify">
Single-crystal-silicon wafers are classified by the orientation of the surface relative to the crystalline axes. The nomenclature is based on the <i>Miller indices</i>. Silicon is a cubic material, constructed from two interpenetrating face-centered cubic lattices of atoms. </p> 

<p align="justify">
The complete silicon unit cell is whon in Fig. 3.1. Every atom is tetrahedrally bonded to four neighbors. The illustration on the left shows an interior atom bound to one corner atom and three face-center atoms(every atom is identical). atom in (111) surface is tetrahedrally bonded to three atoms while atoms on (110) or (100) surfaces are tetrahhedrally bonded to only two atoms beneath the surface, have two potential "dangling" bonds.  The difference in bonding of the atoms on the different crystal surfaces make certain etchants etch anisotrpically.</p> 

<p align = "center">
<img src = "/assets/img/post/2022-07-01-notes-microsystem/3.1_silicon_unit_cell_3.2.png">
</p>
<p align = "center">
Fig 3.1. - The tetrahedral bonding of each atom in the silicon unit cell and Cubic unit cell of silicon.
</p> 

<p align="justify">
Most silicon crystals are grown from a highly purified melt using the Czochralski method(CZ). A small seed crystal with a preselected orientation is inserted into a heated crucible containing a highly purified melt. The seed is gradually pulled out of the melt while the crucible containing the melt is rotated. The melt temperature and pulling speed are controlled to balance crystal growth rate with pulling rate. The schematic of the principle of the Czochralski method is shown in Fig 3.2.</p>

<p align="justify">
An alternative method is called float zone(FZ). Starting with a polysilicon rod, a radio-frequency heater creates a local melted zone that is dragged from one end of the rod to the other. To start the growth, a seed crystal can be used at one end of the rod assembly.</p>

<p align="justify">
Chemical impurities and structural imperfections(point defects, dislocations) specify the quality of silicon crystals. CZ wafers typically have higher amounts of residual chemical impurities, such as carbon, oxygen and heavy metals, compared to FZ wafers because the molten zone tends to carry impurities with it as it sweeps from one end of the rod to the other. However, sometimes it has benefit in certain microelectronic device as the presence of oxygen promotes the migration of point defects during high-temperature process. The higher purity FZ wafers, on the other hand, have requirement of heavy-matal contamination and dislocation. </p>

<p align="justify">
Wafers are supplied in standard diameters and thicknesses, and are polished to mirror smoothness on either one or both sides. </p>

<!-- <p align = "center">
<img src = "/assets/img/post/2022-07-01-notes-microsystem/3.2_Czochralski_method.jpg">
</p>
<p align = "center">
Fig 3.2. - Schematic of the principle of the Czochralski method (left) and illustration of the different steps
</p>  -->

<p align="justify">
Wafers are also characterized by their doping level, n-type or p-type. Dopants are added to the starting melt in order to incorporated uniformly as the crystal grows in CZ crystal growth. Different crystal surface have differnt patterns fo flat edges. Fig. 3.3 show how relative orientation of the secondary wafer flat to thhe larger primary wafer flat provides the identification.</p>

<p align = "center">
<img src = "/assets/img/post/2022-07-01-notes-microsystem/3.3_wafer_flats.png">
</p>
<p align = "center">
Fig 3.2. - Primary and secondary wafer flat are used to identify orientation and types.
</p> 

#### 3.2.1.2 Quartz Wafers
<p align="justify">
Quartz is a hexagonal material, with the z-axis conventionally identified as the hexagonal axis. Because of its piezoelectric properties, single-crystal quartz plays an important role in MEMS. Different from silicon wafer, the standard nomenclature for single-crystal quartz substrates is not based on Miller indices. The basic orientations, such as X-cut and Z-cut quartz, refer to the crystalline axes normal to the plane of the wafer, but AT-cut quartz refer to off-axis orientations that are selected for specific temperature insensitivities fo thir piezoelectric or mechanical properties. 
</p>

### 3.2.2 Wafer Cleaning
The standard set of wafer cleaning steps is called the RCA cleans 
<p align="justify">
1. The standard set of wafer cleaning steps is called the RCA cleans (a 7:3 mixture of concentrated sulfuric acid and hydrogen peroxide, "pirhana")</p>
<p align="justify">
2. Organic residues are removed in a 5:1:1 mixture of water, hydrogen peroxide, and ammonium hydroxide. Oxide will grow on silicon in this step so dilute HF etch should be inserted to remove the oxide.</p>
<p align="justify">
3. ionic contaminants are removed with a 6:1:1 mixture of water, hydrochloric acid, and hydrogen peroxide. </p>

<p align="justify"><b>
No metallic cations should be contained in the cleaning solutions. The RCA cleans must be performed before every high-temperature step(oxidation, diffusion, or chemical vapor deposition).</b></p>

### 3.2.3 Oxidation of Silicon
<p align="justify">
The oxidation reaction is stratghtforward: oxegen reacts directly with the silicon, forming silicon dioxide. The dependence of oxidation rate on oxide thickness has been captured in the <i>Deal-Grove</i> model of oxidation kinetics.</p>

<p align="justify">
If $x_i$ is the initial oxide thickness present on the wafer, then the final oxide thickness $x_f$ is given by</p>

<p align="center">
$x_f=0.5A_{DG}[\sqrt{1+\frac{4B_{DG}}{A^2_{DG}}(t+\tau_{DG})}-1]$
</p>

<p align="justify">
where $A_{DG}$ and $B_{DG}$ are temperature-dependent constants, $t$ is the oxidation time, and $\tau_{DG}$ is given by</p>

<p align="center">
$\tau_{DG}=\frac{x^2_i}{B_{DG}}+\frac{x_i}{B_{DG}/A_{DG}}$
</p>

<p align="justify">
There are two asymptotic regions. At short times, the square root can be expanded to yield the linear rate model:</p>

<p align="center">
$x_f=\frac{B_{DG}}{A_{DG}}(t+\tau_{DG})$
</p>

At long times. parabolic rate model is obtained:
<p align="center">
$x_f=\sqrt{B_{DG}t}$
</p>

<p align="justify">
Overall, about 54% of the total oxide thicknes appears as add thickness. The remaining 46% is conversion of substrate material to oxde.  Fig 3.3. shows the consumption.</p>

<p align = "center">
<img src = "/assets/img/post/2022-07-01-notes-microsystem/3.3_oxidation.png">
</p>
<p align = "center">
Fig 3.3. - Thermal oxidation consumes some of the wafer thickness.
</p> 


<p align="justify">
The diffusion rate of oxygen through oxide can be significantly enhanced if there is water vapor present. It is because water breaks a silicon-oxygen-silicon bond, which is more mobile than molecular oxygen.Hense, the oxidation rate is faster. However, dry oxidation is typically used whtn the highest-quality oxides are required. </p>

### 3.2.4 Local Oxidation
<p align="justify">
When a portion of a silicon wafer is covered with an oxygen diffusion barrier, such as silicon nitride, oxidation cannot occur. As a result, protected regions of a wafer remain at their original heights, while unprotected regions are converted to oxide.  Stress are generated at its edges, creating a tapered oxide called a <i> bird's beak</i> The $LOCOS$ or $Local \  Oxidation$ isolate individual transistors and interconnecting them without creating parasitic transistors beneath the interconnections.</p>


<p align = "left">
<img src = "/assets/img/post/2022-07-01-notes-microsystem/3.4_bird_beak.png">
</p>
<p align = "center">
Fig 3.4. - Bird's beaks and its formation are shown in the fig.
</p> 


### 3.2.5 Doping
<p align="justify">
There are two types of dopants: p-type(holes) and n-tpe(electrons). When a region contains dopants of both types, it is the net dopant concentration in a region that determines its conductivity type, which means an initially p-type regin can be converted to an n-type region by adding more n-type dopant than p-type dopand amount(<i>counter-doping</i>). The process of doping consisstes of two steps: <i>deposition</i> and <i>drive-in</i> </p>

#### 3.2.5.1 Ion Implantation
<p align="justify">
Ion implantation is a process in which a particle accelerator shoots a beam of dopant atoms directly into the wafer. The dopant atoms stay at a particular depth into the substrate, which is called <i>projected range</i>. The depth depends on the ion energy, the ion species, and the material into which the implantation is performed.</p>

<p align="justify">
The fact that ion implantation has a finite range means that surface layers can be used to mask regions of the wafer, preventing the dopant ion from reaching the wafer. Photoresist, silicon dioxide or silicon nitride are commonly used as implant masks. </p>

<p align="justify">
Because direct ion bombardment into a surface can knock surface atoms loose (<i>sputtering</i>), it is normal to do ion implantation through a thin protective layer, such as a few tens of nm of silicon dioxide. This oxide also tends to scatter the ions slightly as they pass through, providing a range of impact angles into the silicon(<i>channeling</i>). The presence of the oxide layer affects the penetration depth into the substrate, and must be taken into account.</p>

#### 3.2.5.2 Drive-In Diffusion
<p align="justify">
Ion implantation provides a certain dose of dopants in a layer near the silicon surface. To redistribute these dopants (as well as to remove any residual defects produced by the implantation process), high-temperature anneals with a protective oxide layer to prevent dopant evaporation in a suitable atmosphere are used. The process for redistribution is called <i>diffusion</i> Temperature affects the diffusion constants, and different dopants also have different temperature dependences.</p>

<p align="justify">
y second-order effects that affect diffusion profiles. Boron can dissolve slowly into overlying oxide, slightly depleting the surface concentration. Diffusion rates are also affected by the presence of point defects and by other dopants. Whether or not oxidation is taking place during the drive-in also have influence in diffusion rates.</p>

### 3.2.6 Thin-Film Deposition
<p align="justify">
Many microelectronic process steps involve the deposition and subsequent patterning of a thin film. </p>

#### 3.2.6.1 Physical Vapor Deposition
<p align="justify">
Physical vapor deposition(PVD), covers two major methods: evaporation, and sputtering. </p>

<p align="justify">
Evapoaration is used primarily for metal and must be donw under high-vacuum. Evaporation with an e-beam is quite directional, allowing interesting shadowing effects to be used. Such method is used to deposit electrodes on the sides of etched quartz microstructures used in accelerometers and rate gyroscopes.</p>

<p align="justify">
Sputtering is a process in which chemically inert atoms, such as argon, are ionized in a glow discharge (plasma). Thhe ions are accelerated into dark space and knocked out to reach the substrate. Sputtering takes palce in a low-pressure gas environment.</p>

<p align="justify">
Though sputtering is less directional than e-beam evaporation, it typically can achieve much higher deposition rates. Therefore, it
is the metallization method of choice in most microelectronic manufacturing.Sputtering can also be used with dielectric films, such as silicon dioxide. Some specialty materials, such as the piezoelectric film zinc oxide and aluminum nitride, are well-suited to sputtering.</p>

#### 3.2.6.2 Chemical Vapor Deposition
Chemical vapor deposition (CVD) 