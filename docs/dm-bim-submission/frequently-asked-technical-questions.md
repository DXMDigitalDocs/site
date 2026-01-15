---
title: FAQs
layout: default
parent: DM BIM Submission
nav_order: 2
---

## Frequently Asked Technical Questions

**Last updated:** 05/11/2024  
**Publisher:** Dubai Municipality  
**Data Type:** Open Data

This document contains a list of common technical questions received by the BIM Support team in relation to BIM submissions.

Sections:
- Model Preparation
- Model Submission
- Submission Self-Assessment
- Misc.

For general BIM mandate questions, visit: https://buildindubai.gov.ae/bim

---

## Model Preparation

### 1. Where can I get the DM BIM standard documentation?
The DM BIM standard and related materials are available on the BuildInDubai website. It is recommended to always use the latest version, as updates are frequent.

### 2. Should I use the DM BIM template or my company template?
You may use your company template. However, the DM BIM template is recommended as it is configured to meet DM BIM requirements and facilitates smoother IFC exports.

### 3. Is a specific BIM authoring tool required?
No. The DM BIM standard is tool-agnostic. Final submissions must be in openBIM IFC format.

### 4. Are there Revit-specific guidelines?
Yes. Refer to **BIM E-Submission_Revit Appendix.pdf** included in the standard.

### 5. How do I fill Appendix-B site, project, and building information?
- In Revit: use **Manage → Project Information**
- In other tools: similar metadata locations apply  
Always verify by exporting to IFC and checking with an IFC viewer.

### 6. Can large BIM models be split into multiple IFC files?
Yes. File naming must strictly follow the standard.  
For Revit users, all files must share the same **Internal Origin** relative to the **Survey Point**.

### 7. How should multiple buildings or building parts be exported?
Requirements:
- One building per IFC model (can be split into multiple files)
- Architectural and structural models must be separate
- **BuildingNum** must be defined (starting from 1)
- **BuildingPartNum** is required only if a building has multiple parts (e.g., podium, towers)

### 8. Must DM level naming conventions be followed?
Yes, for required levels.  
After the standard abbreviation and underscore, custom identifiers are allowed.

### 9. Must DM object naming conventions be followed?
No. They are recommended but not mandatory.

### 10. Which documents define minimum information requirements?
- DubaiBuildingPermitBIMStandards.pdf  
- Appendix-B (attributes)  
- Appendix-C (building, unit, space usage codes)

### 11. Is all Appendix-B information mandatory?
No. Only attributes marked as *required* must be filled. Some are not required for preliminary permits.

### 12. What if Appendix-B attributes do not apply?
Use default values (e.g., FireRating = 0 if not applicable).

### 13. What is Appendix-C for?
It defines allowed building, unit, and space usage codes. Required attributes must use values from this appendix.

### 14. What if I can’t find a usage in Appendix-C?
Contact the BIM support team for guidance.

### 15. Can I check compliance early in modeling?
Yes. Export IFC and upload it to the BIM platform for self-assessment.  
Local checks can be done using:
- IFC viewers
- DM BIM QA/QC app
- DM Building Card Generator

### 16. Which entities are most critical?
All entities matter, but **spaces** and key architectural elements are crucial for:
- Building Card generation
- BUA, GFA, GA, NA calculations

### 17. How can I speed up filling information?
Use schedules and tools like **DiRoots** or **Dynamo** to export to Excel, edit, and re-import.

### 18. Does every space require unit information?
No. Only spaces belonging to units or common facilities require unit data.

### 19. Can international classifications be used?
No. DM usage codes from Appendix-C are mandatory.

### 20. How should parking slots be exported?
Parking slots must be exported as **IfcSpace = PARKING**.

### 21. IFC file size is too large — what should I do?
- Export only required entity types
- Use DM export settings
- Zip all IFCs into one ZIP (max 150 MB)

### 22. Which IFC schema should I use?
IFC4.0 is strongly recommended.

### 23. ZIP file still exceeds size limit?
Remove unnecessary elements (e.g., furniture).  
If still oversized, contact BIM support.

### 24. How should gate level be specified?
Set the **GA_GateLevel** correctly and ensure:
- Project Base Point elevation matches DMD value
- GateLevel attribute is filled

### 25. Should walls and columns be split by level?
Yes. Elements must be hosted at their correct levels to allow correct area calculations.

### 26. Can a shaft be modeled as one space?
No. Shaft spaces must exist on every level.

### 27. IFC predefined type shows “Not Defined”
In Revit 2023+, remove custom `IfcExportAs` parameters and use built-in IFC mappings.

### 28. Can one Revit model export multiple IFCs?
Yes, using:
- Section boxes
- Visible-in-view export options

### 29. What information is required for spaces in units?
Each space must include:
- UnitNo
- UnitUsageCode
- UnitUsageDescription
- UnitExtraInfo

### 30. Parking QA/QC issues appear — why?
PredefinedType is not set to **PARKING**.

### 31. How do I fill level attributes (Appendix-B)?
Select each level and fill required parameters (area attributes).

### 32. Can’t find a space usage code?
Contact BIM support.

### 33. Should IfcSpace height go to ceiling or slab?
- No false ceiling → lowest structural element
- With false ceiling → bottom of false ceiling

### 34. Is there a level naming illustration?
Yes — see the illustration in the document.

### 35. IFC elements hosted on wrong levels — how to fix?
In Revit:
- Manually correct host levels
- Or use `IfcSpatialContainer` parameter

---

## Model Submission

### 38. Can I check models locally before submission?
Yes. Use:
- IFC viewers
- DM QA/QC app
- DM Building Card Generator

### 39. Why are spaces displaced in IFC?
Likely due to gaps in room boundaries. Ensure all room-bounding elements are properly closed.

### 40. Boolean IFC values exporting as false
Greyed-out Booleans in Revit must be explicitly set to True/False.

### 41. Extra levels appear in IFC — is this a problem?
Yes. Only GA_GateLevel, RD_RoadLevel, and floor levels should be exported.

### 42. Are IFC viewers available?
Yes — both free and commercial options exist.

### 43. IFC Site Z value doesn’t match gate level
Not an issue. Site Z comes from Internal Origin. Matching is recommended but not mandatory.

### 44. What are the final submission steps?
- Verify file naming
- Zip all IFC files (no subfolders)
- Ensure file size is within limits

### 45. Are additional files required?
No — only IFC models unless requested.

### 46. Upload error occurs — what now?
- Upload error → file naming / ZIP issue
- Processing error → model issue  
Contact BIM support if needed.

### 47. How do I view uploaded models?
Click **Open BIM Viewer** on the platform.

---

## Submission Self-Assessment

### 48. What should I do after upload?
Download the **Summary Report** and check:
- Naming conventions
- AR/ST models
- Geolocation & gate level
- QA/QC issues
- Space usage
- Building card data
- E-checking rules

### 49. How do I review floors individually?
Use the **Floor** tab in the platform.

### 50. How do I confirm minimum information compliance?
Refer to Question 48 checklist.

### 51. How do I check geolocation accuracy?
Use **Map → View Setbacks** and verify building footprint alignment.

### 52. Why are QA/QC issues classified differently?
- Warning
- Error
- Critical  
Severity depends on impact (e.g., missing building card data = Critical).

### 53. How is the building card generated?
Automatically from BIM model data.

### 54. How are areas calculated?
According to Dubai Building Code rules.

### 55. How can I compare building card with manual calculations?
Download the building card ZIP and review the Excel summary files.

### 56. Why do manual and platform areas differ?
Differences under 5% are expected. Larger differences indicate missing or incorrect data.

### 57. Should I worry about false positive e-checks?
No. The permitting engineer will filter real violations.

### 58. My model meets requirements — what next?
Submit the model for DM engineer review.

### 59. Submission rejected — what should I do?
Review the assessment report, fix issues, and resubmit.

### 60. Does BIM submission approval equal permit approval?
No. It only confirms BIM compliance.

---

## Miscellaneous

### 61. Where can I download BIM standards and samples?
https://buildindubai.gov.ae/bim

### 62. Are there recorded help videos?
Yes — available on the same website.

### 63. Who can I contact for further help?
Email: **geodubai@dm.gov.ae**  
Include the **Project ID** in the subject line.

