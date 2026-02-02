---
title: What Is IFC?
layout: default
parent: IFC Mini Course
nav_order: 2
---

# What Is IFC?

**IFC (Industry Foundation Classes)** is an **open, neutral data standard** used to describe buildings and infrastructure in a **software-independent way**.

It allows BIM information to be **shared, checked, and reused** across different tools, organizations, and project phases.

---

## Why IFC Exists

In many BIM projects:
- Teams use different software
- Native files cannot be reliably exchanged
- Information is lost or misinterpreted
- Long-term access to data is uncertain

IFC was created to solve this.

**Purpose of IFC:**
> Enable reliable, consistent exchange of building information without vendor lock-in.

---

## Who Develops IFC?

IFC is developed and maintained by <a href="https://www.buildingsmart.org/" target="_blank" rel="noopener noreferrer">buildingSMART International</a>.

It is:
- An open standard
- Publicly documented
- Not owned by any software vendor

---

## What IFC Is (Simple Definition)

IFC is:
- A **data schema** (not software)
- A **neutral format** for BIM information
- A way to describe **what a building element is**, not just how it looks

IFC can describe:
- Geometry
- Properties (data)
- Relationships between elements
- Spatial structure of a building

---

## What IFC Is NOT

IFC is **not**:
- A BIM authoring tool
- A replacement for native models
- A "Revit file" or "Archicad file"
- Just a 3D model  

IFC focuses on **information**, not authoring features.

---

## What Kind of Information IFC Contains

### 1. Objects  
Examples:
- IfcWall
- IfcSlab
- IfcDoor
- IfcWindow
- IfcSpace

Each object has a **defined meaning**, not just geometry.

---

### 2. Geometry  
IFC includes:
- 3D shape
- Location
- Orientation

Geometry is important, but **not the main value** of IFC.

---

### 3. Properties (Data)  
Objects can have:
- Names
- Types
- Dimensions
- Fire ratings
- Space usage
- Custom project data

---

### 4. Relationships  
IFC defines how things relate:
- Which elements belong to which storey
- Which spaces are inside which building
- Which components are connected

---

## IFC Spatial Structure (Very Important)

IFC organizes buildings in a clear hierarchy:

- Site  
  - Building  
    - Storey  
      - Space  
        - Elements (walls, slabs, doors...)

This structure allows software and reviewers to **understand the building logically**, not just visually.

---
<img src="{{ site.baseurl }}/assets/ifc-mini-course/image1.png" style="width:50%"  alt="screenshot" />
