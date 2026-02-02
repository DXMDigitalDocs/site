---
title: IFC Core Concepts
layout: default
parent: IFC Mini Course
nav_order: 3
---

# IFC Core Concepts

This document explains the **core concepts behind IFC (Industry Foundation Classes)** in a simple and practical way.

Understanding these concepts is essential before working with:
- IFC export
- IFC validation
- openBIM workflows
- Permits, coordination, or FM use cases

---

## 1. IFC Is a Data Model (Not a File Format)

At its core, IFC is a **data model (schema)**.

This means:
- IFC defines **how building information is structured**
- It defines **types of objects**, their properties, and relationships
- The `.ifc` file is just one way to store that data

Think of IFC as:
> A **language** for describing buildings in a structured way

---

## 2. IFC Objects (Entities)

Everything in IFC is an **object** (also called an *entity*).

Examples:
- `IfcWall`
- `IfcSlab`
- `IfcDoor`
- `IfcWindow`
- `IfcSpace`
- `IfcBuildingStorey`

Each object has:
- A defined meaning
- Expected behavior
- Allowed relationships

### Important Rule
An object’s **type matters more than its shape**.

A wall modeled as the wrong IFC object is **incorrect**, even if it looks right.

---

## 3. Geometry vs Meaning (Semantics)

IFC separates:
- **Geometry** → how something looks
- **Semantics** → what something *is*

Example:
- Two elements may look identical
- One is an `IfcWall`
- One is an `IfcColumn`

IFC allows software and reviewers to:
- Understand intent
- Apply rules
- Perform checks

---

## 4. IFC Properties (Data)

IFC objects can carry **properties**, such as:
- Name
- Type
- Dimensions
- Fire rating
- Space usage
- Custom project data

Properties are grouped into **Property Sets (Psets)**.

Example:
- `Pset_WallCommon`
- `Pset_SpaceCommon`

### Key Idea
IFC is valuable because it carries **data**, not because it shows 3D shapes.

---

## 5. Relationships (How Things Connect)

IFC does not rely only on geometry.  
It explicitly defines **relationships**.

Examples:
- A wall belongs to a storey
- A space is inside a building
- A door fills an opening in a wall

Relationships allow:
- Logical navigation of the model
- Reliable queries
- Rule-based checking

---

## 6. Global Unique Identifiers (GUIDs)

Every IFC object has a **GUID**.

GUIDs:
- Uniquely identify an object
- Stay consistent across exports (if managed correctly)
- Allow tracking changes over time

GUIDs enable:
- Model comparison
- Change detection
- Version control

---

## 7. IFC Spatial Structure (Critical Concept)

IFC organizes buildings using a **spatial hierarchy**.

Typical structure:
- `IfcSite`
  - `IfcBuilding`
    - `IfcBuildingStorey`
      - `IfcSpace`
        - Elements (walls, slabs, doors...)

This structure answers questions like:
- Where is this element?
- Which floor does it belong to?
- Which space contains it?

## Current IFC Schema Versions

IFC has evolved over time. Different versions support different capabilities, domains, and use cases.

Choosing the correct IFC version is important for interoperability and long-term use.

---

### IFC2x3 (Older, Widely Used)

- Mature and stable ISO standard
- Still supported by most BIM tools
- Common in legacy projects and existing mandates
- Limited support for newer concepts

Official specification: [IFC2x3](https://standards.buildingsmart.org/IFC/RELEASE/IFC2x3/FINAL/HTML/)

---

### IFC4 (Core Modern Version)

- Improved data structure and consistency
- Better geometry definitions
- Stronger and clearer semantics
- Recommended baseline for most modern building projects

Official specification: [IFC4.2](https://standards.buildingsmart.org/IFC/DEV/IFC4_2/FINAL/HTML/)

---

### IFC4.3 (Infrastructure Extension)

- Extends IFC beyond buildings
- Supports roads, railways, bridges, and other infrastructure assets
- Part of the IFC for Infrastructure initiative

Official specification:  [IFC4.3](https://ifc43-docs.standards.buildingsmart.org/)

---

### Which IFC Version Should Be Used?

There is no single answer. The correct version depends on:
- Project type (building vs infrastructure)
- Authority or client requirements
- Software support
- Intended use (coordination, permitting, FM, archiving)

In general:
- **IFC4** is recommended for modern building projects
- **IFC4.3** is recommended for infrastructure projects
- **IFC2x3** should be used only when required for compatibility


