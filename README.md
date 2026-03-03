# Obstetrics Notes Collection (ONC)

**Domain:** Clinical / Obstetrics  
**Language:** English  
**Data Type:** History & Physical (H&P) Narratives  
**Size:** 100 notes (50 VBAC, 50 RCS)  
**Format:** `.txt` (raw text) + `.jsonl` (annotations)

---

## Overview
The *Obstetrics Notes Collection (ONC)* contains 100 de-identified obstetric History & Physical (H&P) narratives from patients who either underwent **VBAC (Vaginal Birth After Cesarean)** or **RCS (Repeat Cesarean Section)**.  
Each note represents a clinician’s admission documentation, containing multiple sections such as *past medical history*, *physical examination*, and *impression and plan*.

The dataset is intended for research on:
- Clinical **section segmentation**
- **Discourse structure** of medical narratives

---

## File Structure
```
data/
├── patient_1657.txt
├── patient_1659.txt
└── ...
annotations.jsonl
README.md
```

- **`patient_XXXX.txt`** – Full de-identified H&P narrative text.  
- **`annotations.jsonl`** – Gold-standard section annotations for each note.

---

## Annotation Format
Each line in `annotations.jsonl` is a JSON object:

```json
{
  "note_id": "patient_1657",
  "note_type": "VBAC",
  "sections": [
    {"header": "<none>", "begin": 0 , "end": 167},
    {"header": "history-of-present-illness", "begin": 190, "end": 715},
    ...
  ]
}
```

## Fields

- **`note_id`** – Matches the corresponding `.txt` file in `/data/`  
- **`note_type`** – Delivery group (`VBAC` or `RCS`)  
- **`sections`** – List of text spans with:
  - **`header`** – Section label (e.g., `social-history`, `physical-examination`)  
  - **`begin`, `end`** – Character offsets in the note text  

---


## Data Summary

| Metric | Value |
|--------|-------|
| Total notes | 100 |
| VBAC notes | 50 |
| RCS notes | 50 |
| Avg. note length | ~7,087 characters |
| Avg. sections per note | ~16 |
| Distinct section headers | 30 |



