# GUI-Design-Generation
Extracts structured UI component metadata from GUI layout JSON files in a dataset. Recursively traverses view hierarchies, filters valid elements, and outputs a unified JSON for downstream analysis or training.
Here’s a full **README.md-style** description you can use for your GitHub repository:

---

# GUI Component Extractor 🧩

This repository contains a Jupyter Notebook that extracts structured UI component metadata from a dataset of GUI layout JSON files. It is designed to support preprocessing tasks for GUI understanding, layout analysis, or training data preparation in deep learning-based UI generation workflows.

---

## 📌 Overview

Modern GUI datasets often store screen layouts as hierarchical JSON structures. This notebook automates the process of:

* Recursively traversing GUI view trees
* Identifying valid UI components based on their `class` and `bounds`
* Preserving parent-child relationships and depth
* Exporting all extracted metadata into a single JSON file for easy downstream use

---

## 📁 Input Dataset Structure

The input folder should look like this:

```
/ExperimentalDataset/
    App1/
        screen1.json
        screen2.json
    App2/
        screen1.json
        ...
```

Each `.json` file represents the view hierarchy of a GUI screen.

---

## 📤 Output

After processing, the notebook generates:

```
/ExperimentalDataset_phase1_output/
    manually_processed_components.json
```

This output JSON contains a flat list of all valid UI components across all apps and screens, including fields like:

* `id`
* `app`
* `screen`
* `class`
* `bounds` (x1, y1, x2, y2)
* `depth`
* `parent_id`

---

## ⚙️ How It Works

1. Iterates over each app folder and screen JSON.
2. Skips invalid or unexpected formats.
3. Extracts components using depth-first traversal.
4. Saves all processed components to a single JSON file.

---

## 🔧 Requirements

This notebook is designed to run in Google Colab and uses only standard Python libraries:

* `os`
* `json`
* `pathlib`

---

## ✅ Use Cases

* GUI component dataset preparation
* Preprocessing for layout generation models
* Hierarchical structure analysis of UI screens

---

Let me know if you also want a `.py` script version of this notebook or auto-generation of GitHub topics/tags.
