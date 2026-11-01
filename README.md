# LumenFlow

Volumetric segmentation of membrane-bound compartments in cryo-electron tomograms using deep learning and synthetic data

Membrane segmentation networks such as TomoSegNet output the membrane itself.
Many analyses need the volume it encloses, the lumen: organelle and vesicle
volumes and shapes, or whether a macromolecule lies inside a compartment.
LumenFlow extends TomoSegNet's simulation-based training from membranes to
lumens.

- **Semantic baseline:** a 3D nnU-Net predicts lumen masks.
- **Instance segmentation:** inspired by Omnipose, a network predicts a
  foreground probability, an eikonal distance field and its flow field.
  Following the flows separates individual compartments, including touching
  ones and ones with gaps in their membranes.
- **Synthetic training data:** Curvatubes geometries simulated as tomograms
  with PolNet give exact instance-level lumen labels.
- **Evaluation:** synthetic test sets and experimental tomograms, with
  semantic and instance metrics.
