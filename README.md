# Do Pre-trained Vision-Language Models Encode Object States?

This repository contains the dataset used in the paper  
**"Do Pre-trained Vision-Language Models Encode Object States?"**  
by Kaleb Newman, Shijie Wang, Yuan Zang, David Heffren, and Chen Sun  
[[arXiv:2409.10488](https://arxiv.org/abs/2409.10488)]

---

## 🗂️ Dataset Overview

#### 🔹 `ChangeIT-Frames-Full/`
The full image dataset (~25K images) extracted from the [ChangeIt video dataset]((https://github.com/soCzech/ChangeIt)). Each image corresponds to a key frame depicting an object in a particular physical state.

#### 🔹 `ChangeIT-Subset-Crop/`
A golden subset (~1.7K images) of **human-verified annotations**, containing **cropped images** around the object bounding box. Used for fine-grained state recognition evaluation.

#### 🔹 `ChangeIT-Subset-Images/`
Same golden subset as above, but with **full uncropped images**. Used to compare performance on full vs. object-centric inputs.

#### 🔹 `annotations/`
Frame-level annotations for each video. This is derived from the ChangeIT dataset

---

## 🔍 Utils folder

#### 🧠 `classification_states.py`
Defines state labels for each object category.  
- `q`: All possible states for a category  
- `a`: Initial and terminal states, used for structured state transition evaluation

#### 🧮 `dicts.py`
Parses frame-level annotation CSVs into a dictionary (`cat_dicts`) mapping each category to its annotated videos and corresponding frame-level state labels.

#### 🧾 `golden_subset_annotations.py`
Processes and aligns annotations with selected subset frames from `ChangeIT-Subset-Images/`, returning filtered ground-truth labels and category associations.



---

## 📊 Key Findings from paper

- VLMs perform well on object recognition but struggle with **fine-grained physical state recognition**.
- Even with human-labeled crops and object-centric modifications, models fail to distinguish between states like “peeled apple” vs. “cut apple”.
- Patch-level models (e.g., FLAVA) outperform others in distractor scenarios, possibly due to better region-text binding.

Read the full paper for more insights: [arXiv:2409.10488](https://arxiv.org/abs/2409.10488)

---


## 🧠 Citation

If you use this dataset or code, please cite:

```bibtex
@article{newman2024objectstates,
  title={Do Pre-trained Vision-Language Models Encode Object States?},
  author={Newman, Kaleb and Wang, Shijie and Zang, Yuan and Heffren, David and Sun, Chen},
  journal={arXiv preprint arXiv:2409.10488},
  year={2024}
}
