# Mop Joint Redesign

## Overview 
The Bona mop is used for cleaning and maintaining hardwood flooring. After just a couple of years, my first mop failed at a thin, filleted section near the joint between the handle and mop head, and now my second unit is showing similar signs of expected failure. I investigated the root cause and developed a redesigned geometry to reduce stress concentrations and improve durability. Using CAD modeling and finite element analysis, I evaluated the original design and iteratively refined the model, achieving over a 60% reduction in peak stress.

## Problem Definition
The mop head is connected to the handle via a double-pivoting joint, allowing for multi-axis motion. The failure occurred in the plastic component at the end of the handle, specifically at the protruding section where a pin connects it to the intermediate joint piece. This section is relatively thin (~1/4") with a small fillet radius (~5/128") at its base. This sharp transition creates a stress concentration under the bending loads applied during typical use. This repeated loading and stress concentration led to visible signs of material degradation, including discoloration and deformation (creep). Since my replacement mop is experiencing the same symptoms as my first mop, this suggests a design flaw rather than an isolated incident.

The objective of this project was to reduce stress concentrations in this critical section through a geometric redesign, which would improve the durability and lifespan of the component.

<div style="display: flex; gap: 8px; margin-bottom: 10px;">

  <div style="flex: 1; text-align: center;">
    <img src="../assets/images/Bona Mop joint.JPG" style="width: 100%;">
  </div>

  <div style="flex: 1; text-align: center;">
    <img src="../assets/images/Bona Mop discoloration.JPG" style="width: 100%;">
  </div>

</div>

## Engineering Analysis
To better understand the root cause of failure, I modeled the failing part in Autodesk Fusion. As force is applied through the handle, the geometry creates a bending moment at the cantilevered section. I applied a simplified loading case assuming a mopping force of 50 N at 45°, resulting in a bending moment of 0.2 N*m at the joint.

![CAD Assembly](../assets/images/Assembly with annotations.png)

Based on standard stress concentration charts for a filleted bar in bending (D/d ≈ 3, r/d ≈ 0.16), the estimated stress concentration factor K ≈ 1.5. This indicates that local stresses at the fillet could be roughly 50% higher than the nominal bending stress.

My initial hand calculations suggested that the stresses under typical forces will remain well below the material's yield strength, indicating that static failure is unlikely to be the primary cause of failure. Instead, the observed discoloration, creep, and cyclic nature of loading that occurs during mopping indicate that fatigue failure is more likely to occur.

This analysis established that reducing local stress concentrations through a geometric redesign of the fillet radius would improve fatigue resistance and long-term durability without requiring major changes to the part geometry or manufacturing process.

## CAD Models & FEA Results

I modeled the joint component based on measurements of the original part. This model was used as the baseline for the analysis and design iterations. As is observed in the FEA analyses below, the cantilevered geometry demonstrates a clear stress concentration scenario, where abrupt changes in cross-section amplify local stresses under bending. As the fillet radius increases, the transition in cross-section becomes smoother, resulting in smaller stress concentrations.

### Original Configuration - 5/128" fillet radius
<div style="display: flex; gap: 8px; align-items: stretch; margin-bottom: 80px;">

  <div style="flex: 0.8; text-align: center;">
    <img src="../assets/images/Config 1.png"
         style="width: 100%; height: 100%; object-fit: contain;">
    <p><em>Original Configuration CAD model</em></p>
  </div>

  <div style="flex: 1.2; text-align: center;">
    <video controls playsinline webkit-playsinline
           style="width: 100%; height: 100%; object-fit: contain;">
      <source src="../assets/videos/Config 1 VM Stress.mp4" type="video/mp4">
    </video>
    <p><em>Original Configuration FEA simulation</em></p>
  </div>

</div>

The original configuration has a fillet radius of 5/128". Under the simulated loading conditions, the resulting Von Mises stress peaks at around 1.66 MPa (240 psi). The estimated yield strength of HDPE typically ranges from about 18 - 30 MPa (2600 - 4500 psi).

### Configuration 2 - 1/16" fillet radius
<div style="display: flex; gap: 8px; align-items: stretch; margin-bottom: 80px;">

  <div style="flex: 0.8; text-align: center;">
    <img src="../assets/images/Config 2.png"
         style="width: 100%; height: 100%; object-fit: contain;">
    <p><em>Configuration 2 CAD model</em></p>
  </div>

  <div style="flex: 1.2; text-align: center;">
    <video controls playsinline webkit-playsinline
           style="width: 100%; height: 100%; object-fit: contain;">
      <source src="../assets/videos/Config 2 VM Stress.mp4" type="video/mp4">
    </video>
    <p><em>Configuration 2 FEA simulation</em></p>
  </div>

</div>

The second configuration has a fillet radius of 1/16". Under the same loading conditions, the resulting Von Mises stress peaks at around 1.45 MPa (210 psi). This is a reduction of approximately 13%.

### Configuration 3 - 1/8" fillet radius
<div style="display: flex; gap: 8px; align-items: stretch; margin-bottom: 80px;">

  <div style="flex: 0.8; text-align: center;">
    <img src="../assets/images/Config 3.png"
         style="width: 100%; height: 100%; object-fit: contain;">
    <p><em>Configuration 3 CAD model</em></p>
  </div>

  <div style="flex: 1.2; text-align: center;">
    <video controls playsinline webkit-playsinline
           style="width: 100%; height: 100%; object-fit: contain;">
      <source src="../assets/videos/Config 3 VM Stress.mp4" type="video/mp4">
    </video>
    <p><em>Configuration 3 FEA simulation</em></p>
  </div>

</div>

The third configuration has a fillet radius of 1/8". Under the same loading conditions, the resulting Von Mises stress peaks at around 0.84 MPa (122 psi). This is a reduction of approximately 49%.

### Configuration 4 - 1/4" fillet radius
<div style="display: flex; gap: 8px; align-items: stretch; margin-bottom: 80px;">

  <div style="flex: 0.8; text-align: center;">
    <img src="../assets/images/Config 4.png"
         style="width: 100%; height: 100%; object-fit: contain;">
    <p><em>Configuration 4 CAD model</em></p>
  </div>

  <div style="flex: 1.2; text-align: center;">
    <video controls playsinline webkit-playsinline
           style="width: 100%; height: 100%; object-fit: contain;">
      <source src="../assets/videos/Config 4 VM Stress.mp4" type="video/mp4">
    </video>
    <p><em>Configuration 4 FEA simulation</em></p>
  </div>

</div>

The fourth configuration has a fillet radius of 1/4". Under the same loading conditions, the resulting Von Mises stress peaks at around 0.65 MPa (94 psi). This is a reduction of approximately 61%.

While increasing the fillet radius significantly reduced local stress, the returns in stress reduction start to slow down as the fillet grows. Also, excessively large fillets would eventually interfere with the adjacent geometry and prevent the joint from having its full range of motion.

## Experimental Validation

To supplement the analytical and FEA results, I conducted a simple comparative load test using 3D printed versions of both the original and redesigned joint geometries.

<div style="display: flex; gap: 8px; margin-bottom: 30px;">

  <div style="flex: 1; text-align: center;">
    <img src="../assets/images/Printed Heads.jpeg" style="width: 100%;">
    <p><em>Configurations 1 & 4, 3D printed</em></p>
  </div>

  <div style="flex: 1; text-align: center;">
    <img src="../assets/images/test-setup.jpg" style="width: 100%;">
    <p><em>Testing setup</em></p>
  </div>

</div>

I assembled a test rig by suspending a bucket off the end of a bolt secured to the printed part through the pivot hole. I then gradually added sand until structural failure occurred.

While the printed components do not perfectly replicate the material properties or manufacturing characteristics of the original injection-molded HDPE part, the experiment provided a useful comparative evaluation between the two geometries under consistent loading conditions.

### Original Configuration Test

<div style="display: flex; gap: 8px; margin-bottom: 30px;">

  <div style="flex: 1; text-align: center;">
    <img src="../assets/images/config1-failure.jpg" style="width: 100%;">
    <p><em>Yield failure</em></p>
  </div>

  <div style="flex: 1; text-align: center;">
    <img src="../assets/images/config1-catastrophic.jpg" style="width: 100%;">
    <p><em>Catastrophic failure</em></p>
  </div>

</div>

The original configuration withstood about 9 pounds of sand in the bucket before failing.

### Configuration 4 Test

<div style="display: flex; gap: 8px; margin-bottom: 30px;">

  <div style="flex: 1; text-align: center;">
    <img src="../assets/images/config4-failure.jpg" style="width: 100%;">
    <p><em>Yield failure</em></p>
  </div>

  <div style="flex: 1; text-align: center;">
    <img src="../assets/images/config4-catastrophic.jpg" style="width: 100%;">
    <p><em>Catastrophic failure</em></p>
  </div>

</div>

Configuration 4 withstood about 10 pounds of sand in the bucket before failing.

The redesigned configuration with the increased fillet radius sustained approximately 10% greater load before failure compared to the original geometry. Although the real-world failure mechanism of my mop was fatigue rather than static failure, the experiment still supports the underlying design principle that reducing stress concentrations improves structural performance and durability.

### Future Experimental Improvements

Future testing could better replicate real-world operating conditions through cyclic fatigue loading rather than static yield testing alone. Additional improvements may include using injection-molded test parts with material properties closer to the original HDPE component, as well as incorporating strain or displacement measurements to further validate analytical and FEA predictions.

## Key Takeaways

This project demonstrated how relatively small geometric changes can significantly affect the strength and durability of mechanical components. Through a combination of failure analysis, CAD modeling, FEA simulation, iterative design, and experimental validation, I developed and evaluated a practical design improvement grounded in both analytical and physical testing methods.
