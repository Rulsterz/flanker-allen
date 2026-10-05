# Human attention scan versus a mouse visual-to-thalamus map

This project tested whether a public human attention-task dataset shows the visual-to-thalamus projection already mapped in the mouse brain.

The human data were from a public flanker scan at OpenNeuro ds000102. Each trial was marked congruent or incongruent. The signal was averaged in a back-of-brain mask and a deep central mask, over the first 4 seconds and the first 8 seconds after the marker. Each scan took 2 seconds, so those windows are 2 and 4 scans. The masks are rough locations in the raw image, not labeled atlas regions.

NumPy stored the scan matrix and the density vector. SciPy filtered the series and ran the contrast.

The scan matrix was 64×64×40×146, from four subjects and both runs, 192 trials. In the first 4 seconds, incongruent trials were 0.33 higher in the back-of-brain mask and 0.56 higher in the deep central mask. Neither difference was reliable (p=0.14 and p=0.20). In the first 8 seconds, the back-of-brain difference was 0.35 (p=0.063). The deep central difference was 0.81 (p=0.017). That mask was only a rough central location, not a region labeled thalamus.

In the mouse atlas, the primary visual cortex sends a dense projection to the dorsal lateral geniculate (0.143) and the ventral lateral geniculate (0.140), a weaker one to the lateral posterior nucleus (0.084), and a thin one to the thalamus as a whole (0.022).

Conclusion: the human result does not match the mouse projection. The back-of-brain difference was weak at both 4 and 8 seconds. The only clearer difference was in the deep central mask at 8 seconds, and that mask was a rough central location, not a region labeled thalamus.

Data: OpenNeuro ds000102; Allen Mouse Brain Connectivity Atlas.

## Figure

The orange bars are larger. That is not a thalamic finding. The deep central mask is a rough central location, not a region labeled thalamus. The back-of-brain mask is the visual-cortex stand-in, and its difference was weak at both 4 and 8 seconds.

![Axial slice, Allen prior, and flanker contrast](figure.png)

Caption: left, OpenNeuro ds000102 sub-01 run 1, axial slice 20 of 40, native echo-planar imaging, not an atlas label. Top right, Allen prior from 33 wild-type primary visual cortex injections: dorsal lateral geniculate 0.143, ventral lateral geniculate 0.140, lateral posterior nucleus 0.084, thalamus 0.022. Bottom right, incongruent minus congruent in four subjects and 192 trials. Back-of-brain mask 0.33 at 4 seconds (p=0.14) and 0.35 at 8 seconds (p=0.063). Deep central mask 0.56 at 4 seconds (p=0.20) and 0.81 at 8 seconds (p=0.017). The tall orange bar is the clearer deep-central difference, not evidence that the patterns match the mouse projection.
