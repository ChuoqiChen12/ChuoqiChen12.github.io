---
title: Microsystem Design -- Part 1 Getting Started
author: Chuoqi Chen
date: 2022-07-01 10:00:00 -0400
categories: [Book Notes, Microsystem Design]
tags: [mems]
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

## Chapter 1 Introduction

> *What's in a name?...A rose by any other name would smell as sweet.* - W. Shakespeare in *Romeo and Juliet*

### 1.1 Microsystems vs. MEMS

#### 1.1.1 What are they?
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


#### 1.1.2 How are they made?
<p align="justify">
"micromachining": Lithographic techiniques require flat susbstrates. Silicon is often used. Lithography offers in-place sub-micron precision on dimension scales from micron and milimeter. Thin-fillm deposition and etching techiniques in combination with wafer-bonding techniques allow patterning of the third dimension. Integrated circuits and partition the microsystem into susbsystems are two ways to build the system. Encapsulation and packaging of the components into a system impact the design too. </p>

#### 1.1.3 What are they made of?
<p align="justify">
The choice of materials is determined by microfabrication constraint. Most of these are inorganic materials, including silicon, silicon dioxide, silicon nitride, aluminum and tunsten. Certain polymer might be use as well. </p>

<p align="justify">
Certain properties  are critical in device performance, for examplt, the elastic modulus or residual stress of a suspended beam.</p> 

#### 1.1.4 How are they designed? 
<p align="justify">
On one level, the designer mush documen the need and specificaiton for a proposed microsystem. At another level, for each proposed approach, one must deal with details of partitioning the system into components, materials selection and the responding fabrication sequences for each componen, methods for packaging and assembly.</p>

<p align="justify">
Quantitive models play a key role in the design process.(perdiction, troubleshooting, evalution)</p>

### 1.2 Markets for Microsystems and MEMS
> *Forecasting is difficult. expecially the future. - Chinese forture cookies*

### 1.3 Case Studies

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

## Chapter 2 An Approach To MEMS Design
> *If technology-driven design is a hammer looking for a nail, then markei-driven design is a nail looking for a hammer. A good designer will match hammers to nails, regardless of which comes first. - Anonymous*

### 2.1 Design: The Big Picture
<p align="justify">
Examine the big picture, including difficult subhects such as creativity and invention, market opportunities, and choices of technologies, system architectures, and manufacturing methods.
</p>

#### 2.1.1 Device Categories
<ul>
<li><p align="justify"><b>Technology Demonstrations:</b> small numbers of working devices are needed to test a device concept or push the capabilities and limits of a particular fabrication technology.(require only a handful of working devices. Device-todevice consistency is not usually important.)</p></li>
<li><p align="justify"><b>Research Tools:</b> components or fully systems have the porpose of performing a highly specialized task. (must typically be calibrated, and should have repeatable behavior.)</p></li>
<li><p align="justify"><b>Commercial Products:</b>The numbers of working devices and the degree of precision and accuracy needed depend on the market.(Device-todevice consistency and high manufacturing yield are likely to be of paramount importance.)</p></li>
</ul>

#### 2.1.2 High-Level Design Issues
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

#### 2.1.3 The Design Process