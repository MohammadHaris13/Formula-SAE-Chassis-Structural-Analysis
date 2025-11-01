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

<img width="756" height="419" alt="FSAE" src="https://github.com/user-attachments/assets/7385f0c8-8c04-4aff-94e6-87c2825ebd7c" />

---

## Mesh

<img width="1624" height="643" alt="Mesh" src="https://github.com/user-attachments/assets/ef801493-1b40-4e99-bca2-372eadec26e8" />

---

## Torsion Test


<img width="1626" height="633" alt="Tortion Test" src="https://github.com/user-attachments/assets/6f13b6cf-ecf4-4640-84bc-40f3811aed93" />


https://github.com/user-attachments/assets/c4e4fbb3-7d82-434f-8003-92dd4c4b31ad



https://github.com/user-attachments/assets/a803d8b5-8c20-4e09-adc2-01764c7e51b8



https://github.com/user-attachments/assets/b18f10dd-3866-42e2-a9d9-655f8e299893



https://github.com/user-attachments/assets/25c98309-6e4f-4a44-ab49-b0362dc2dee7


---


## Cornering Test


<img width="1625" height="647" alt="Cornering Test" src="https://github.com/user-attachments/assets/4efa5068-1909-4138-94a2-f3e7df19b7ea" />


https://github.com/user-attachments/assets/db11778a-8c8e-450a-a9d7-28575780be4d



https://github.com/user-attachments/assets/da63c805-7773-46cd-a9d3-1a0234b98ae2



https://github.com/user-attachments/assets/bdc39dc8-0174-44c5-9a28-aa5be59186c4



https://github.com/user-attachments/assets/50868c34-a0c1-4366-ac07-6e526665d161



https://github.com/user-attachments/assets/c89665d0-ae48-40a4-924f-b0fad14fde72


---

## Aero+Cornering Test


<img width="1625" height="637" alt="Aero+Cornering Test" src="https://github.com/user-attachments/assets/79a11aad-82db-4349-9211-11b8deff2491" />


https://github.com/user-attachments/assets/4b71fdc7-746a-436b-9a1f-baec0463965a



https://github.com/user-attachments/assets/a961ffc2-8481-4064-8b12-b9c4d8d63d82



https://github.com/user-attachments/assets/5cbd41f8-447f-4607-b863-4f6d3ada4299



https://github.com/user-attachments/assets/1ad2313e-a621-4f9e-a24d-43dd2a9c8e73

---

## Frontal Impact Test


<img width="1626" height="635" alt="Frontal Impact Test" src="https://github.com/user-attachments/assets/825a8c5f-f0e4-4195-9774-1dae1b75b075" />


https://github.com/user-attachments/assets/8bc0cdd7-e476-4414-9753-3e92060575ab



https://github.com/user-attachments/assets/28b4826a-9265-44fd-821e-b8f7c8babd26



https://github.com/user-attachments/assets/6f17229e-48a5-4f09-9892-92dab95c8150



https://github.com/user-attachments/assets/4acd9339-2032-4f3d-862e-599f2fa662ee



https://github.com/user-attachments/assets/2b6c2e95-3b4f-4dd1-8109-46d64ed10266

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














