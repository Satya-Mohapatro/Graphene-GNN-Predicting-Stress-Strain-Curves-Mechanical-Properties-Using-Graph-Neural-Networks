# Graphene-GNN: Predicting Mechanical Response of Defected Graphene Using Graph Neural Networks
**Author:** Satyanarayan Mohapatro    
**In Collaboration With:** CAMMP (Center for Advanced Modeling of Materials & Manufacturing Processes)

This repository contains an end-to-end machine learning pipeline for predicting the **mechanical behavior of defected graphene structures** using **Graph Neural Networks (GNNs)**.  
The project integrates materials physics, graph representation learning, and deep neural models to achieve **high-fidelity predictions** of:

- **Young’s Modulus**
- **Fracture Strain**
- **Full 801-point Stress–Strain Curves**

Achieved **R² ≈ 0.9925** for curve prediction — comparable to physics-based simulations but **100× faster**.

---

##  Project Highlights

### **Phase 1 — Synthetic Stress–Strain Data Generation**
- Input: Raw Excel curves for **0%, 2%, 4%, 6%, 8%, 10%** void fractions  
- Interpolated all curves to a **common 801-point strain grid**  
- Generated **500 synthetic stress–strain curves** for random void fractions (0–10%)  
- Extracted:
  - **Young’s Modulus**
  - **Fracture Strain**

### **Phase 2 — GNN for Property Prediction**
- Graphene modeled as a **2D lattice (18×18 grid)**  
- Nodes removed based on void fraction → defect simulation  
- Node features: *(x, y, degree, void_fraction)*  
- GNN predicts:
  - **Young’s modulus**
  - **Fracture strain**

**Best model performance:**
- Young’s Modulus R²: **0.981**
- Fracture Strain R²: **0.812**

### **Phase 3 — GNN for Full Stress–Strain Curve Prediction**
- Output: **801-point stress–strain curve**  
- 4-layer GINE/GNN model  
- Edge-conditioned message passing  
- Log-scaled stress normalization  
- Smooth L1 loss for curve stability  
- **Final performance:**  
  - RMSE: **3.71 GPa**
  - R²: **0.9925**

---

##  Results

### **Property Prediction**
| Target           | RMSE     | R²      |
|------------------|----------|---------|
| Young’s Modulus  | 20.43    | 0.981   |
| Fracture Strain  | 0.0237   | 0.812   |

### **Full Curve Prediction**
- **Test RMSE:** 3.713 GPa  
- **R²:** 0.9925  

---

##  Technologies Used

- **Python 3.10**
- **PyTorch**
- **PyTorch Geometric (PyG)**
- **NetworkX**
- **scikit-learn**
- **matplotlib / seaborn**
- **NumPy / pandas**

---

##  Acknowledgments

Special thanks to **Akash Sir** and **CAMMP** for their consistent guidance and evaluation support throughout the project.

---

##  Contact

For any queries or discussions:

**Satyanarayan Mohapatro**  
Email: *satyaamohapatro@gmail.com*  
 
---

