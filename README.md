# Formula SAE Chassis Structural Analysis

This project focuses on the **structural analysis of a Formula SAE chassis** using **ANSYS Workbench (SpaceClaim + Mechanical)**. The objective was to evaluate the **stiffness, strength, and load-carrying capability** of the spaceframe chassis under multiple realistic loading conditions.

---

## Project Overview

The chassis was analyzed under **torsion**, **cornering**, **aero + cornering**, and **frontal impact** load cases.
The workflow followed a step-by-step approach from geometry simplification and beam extraction to joint setup, meshing, boundary condition application, and post-processing.

---

## Workflow Summary

### **Step 1: Beam Extraction & Profile Assignment**

* Imported the chassis geometry into **ANSYS SpaceClaim**.
* Extracted **beam elements** from 3D solid members.
* Used the **Connect Tool** to join open ends (max distance = 25 mm).
* Assigned **tubular beam profiles**:

  * Outer Diameter = 16 mm
  * Inner Diameter = 12.5 mm
* Verified connectivity and geometry integrity before import to Workbench.

---

### **Step 2: Suspension Arms & Wishbone Modeling**

* Imported **coordinate data (.txt)** for suspension points and created beams via **3D sketches**.
* Constructed **upper and lower wishbones** using coordinate import and beam creation tools.
* For rear arms:

  * Created reference planes → used sketch tools → converted sketches to beams.
  * Mirrored geometry with **Mirror Plane** for symmetry.
* Split beams where required for later boundary condition definition.
* Combined all chassis members into a single shared part for import to **ANSYS Mechanical**.

---

### **Step 3: Joint Definition & Meshing**

* Assigned **Structural Steel** as material.
* Created **spherical** and **revolute joints** via *Object Generator*:

  * Reference = Wishbone Vertices
  * Mobile = Chassis Vertices
  * Max Distance = 5 mm
* Added **spring connections** (longitudinal stiffness = 40 N/mm) between chassis and uprights.
* Generated **5 mm element-size mesh** for all beam members ensuring uniform discretization.

---

### **Step 4: Load Cases & Boundary Conditions**

#### 🔹 **Torsion Test**

* ±1500 N applied on front uprights in opposite directions.
* Rear suspension mounts simply supported (no translation, free rotation).
* Output: total deformation and stress via **Beam Tool**.
* Stresses below yield → safe design under torsional load.

#### 🔹 **Cornering Test**

* 1 g lateral acceleration (X-direction) + standard gravity (Y-direction).
* Added **point masses**: 70 kg driver and 25 kg engine.
* Fixed supports applied at upright vertices.
* Verified lateral stiffness and stress distribution.

#### 🔹 **Aero + Cornering Test**

* 2 g aerodynamic acceleration (X-direction) + gravity (Y-direction).
* Uprights fixed, same as cornering setup.
* Evaluated combined aero-cornering loads and deformation behavior.

#### 🔹 **Frontal Impact Test**

* 30 000 N frontal force applied on front bulkhead (Z-direction).
* Rear suspension nodes simply supported.
* Observed load transfer path and rear-frame stress concentration.
* (Note: static simplification — dynamic crash simulation recommended for future work.)

---

## Results Summary

| Test Type            | Load Applied      | Boundary Condition    | Observation / Result             |
| -------------------- | ----------------- | --------------------- | -------------------------------- |
| **Torsion Test**     | ±1500 N           | Rear simply supported | High rigidity, safe stress       |
| **Cornering Test**   | 1 g + Gravity     | Uprights fixed        | Stable lateral stiffness         |
| **Aero + Cornering** | 2 g + Gravity     | Uprights fixed        | Slight rise in deformation       |
| **Frontal Impact**   | 30 000 N (Z-dir.) | Rear simply supported | Stress localized near rear frame |

---

## Key Learnings

* Gained hands-on experience in **beam-based chassis modeling** within ANSYS SpaceClaim.
* Understood **load path distribution** and **torsional rigidity** behavior.
* Applied **multiple static load cases** and analyzed corresponding stress/deformation results.
* Strengthened skills in **meshing, joint definition, and boundary setup** for vehicle structures.

---

## Tools & Technologies

* **ANSYS Workbench** (SpaceClaim + Mechanical)
* **Static Structural Module**
* **Finite Element Analysis (FEA)**

---

## Skills Demonstrated

* Beam & Joint Modeling
* Structural Strength Evaluation
* Vehicle Chassis Design
* Load & Boundary Condition Setup
* Meshing & Validation
* Design Optimization & Safety Assessment

---

## Results Visualization

---
<img width="756" height="419" alt="FSAE" src="https://github.com/user-attachments/assets/50c74872-24f0-40ff-8f78-c592a18d7fc1" />


---

## Mesh

<img width="1624" height="643" alt="Mesh" src="https://github.com/user-attachments/assets/142dea09-2def-4924-90f7-f73237f60956" />

---

## Torsion Test


<img width="1626" height="633" alt="Tortion Test" src="https://github.com/user-attachments/assets/d94ffe50-f033-481f-ad23-ca0e9263b7ea" />




https://github.com/user-attachments/assets/4da9d7c4-24f4-495a-b828-9308eb6f3f71



https://github.com/user-attachments/assets/63342edc-1288-4a07-b9cf-999541a4201b



https://github.com/user-attachments/assets/a66a56ea-d420-425b-bc28-45cec74be1a8



https://github.com/user-attachments/assets/5f4800ea-6a1d-4420-a5d8-ba2611da757e




---


## Cornering Test


<img width="1625" height="647" alt="Cornering Test" src="https://github.com/user-attachments/assets/87989242-064f-4076-bd38-b6028da0fac8" />



https://github.com/user-attachments/assets/7a3b465f-8112-4d7a-8155-477ec235718d



https://github.com/user-attachments/assets/4a05a36a-43f2-4208-a59e-854dcd92e088



https://github.com/user-attachments/assets/f36ace55-61c6-4d74-a427-7fbe6e6a4c48



https://github.com/user-attachments/assets/526cacb4-80b9-4e4e-8545-1edc0d8362c2



https://github.com/user-attachments/assets/515cb4d5-5187-4946-b071-b268490d2f64



---

## Aero+Cornering Test



<img width="1625" height="637" alt="Aero+Cornering Test" src="https://github.com/user-attachments/assets/e680ced7-5fc3-41ad-91ea-6385d5b1a9e1" />



https://github.com/user-attachments/assets/a5f32eff-e223-4a44-8752-c8ea27b2e019



https://github.com/user-attachments/assets/6a9ad24e-6c03-45a8-8fb0-e2aa7f100633



https://github.com/user-attachments/assets/027fcfb7-717a-4523-a9b0-6763cc694d7f



https://github.com/user-attachments/assets/c7361a27-7bc0-4a9d-a2e7-918f18341153




---

## Frontal Impact Test


<img width="1626" height="635" alt="Frontal Impact Test" src="https://github.com/user-attachments/assets/068aafee-f165-4af7-82bf-771a1f4f59a5" />




https://github.com/user-attachments/assets/99520482-5e3e-4650-84bf-d4591e729680



https://github.com/user-attachments/assets/0de76065-df44-4fff-966d-eceb817f387f



https://github.com/user-attachments/assets/db54f99e-ddcb-4f65-a603-14c2cbd2f4e7



https://github.com/user-attachments/assets/5235b682-80e8-4c4b-b76f-a3aaedc8ae3b



https://github.com/user-attachments/assets/4890b35a-2bd1-45b2-90b1-019527b10514




---

## Conclusion

The Formula SAE Chassis Analysis effectively validated the frame design for strength, stiffness, and vibration stability under various real-world racing conditions such as torsion, cornering, aerodynamic, and impact loads.
The FEA results confirmed that stresses remained below the material’s yield strength, ensuring structural integrity and driver safety without unnecessary weight penalties.
The torsional stiffness and modal frequencies were found to be within the desirable range for high-performance handling, minimizing chassis flex and vibration coupling. This confirms that the chassis design provides an optimal balance between lightweight construction and structural robustness.
This project provided deep insight into racecar structural analysis, finite element validation, and design-for-performance optimization using ANSYS Workbench — bridging the gap between CAD design and real-world engineering validation.

---

### Author
**Mohammad Haris**  
Final Year B.Tech – Mechanical Engineering  
VIT-AP,Amaravati   
[Linkedin Profile](https://linkedin.com/in/mohammad-haris-13032002) | [Email](mailto:mohammaddharis1303@gmail.com)

---














