This folder contains all the notebooks used to extract mean signal intensities from substantia nigra pars compacta (SNpc), locus coeruleus (LC), putamen and a white matter (WM) region in frontal cortex, across the MR modalities and maps.
1. Mean signal intensity extraction from WM region in frontal cortex
   * wm_extraction.ipynb

2. Mean signal intensity extraction from SNpc
   * sn_extraction.ipynb

3. Mean signal intensity extraction from putamen
   * putamen_extraction.ipynb

4. Mean signal intensity extraction from LC (LC extraction was performed in batches)
   * lc_extraction.ipynb
   * lc_extraction_2.ipynb
   * lc_extraction_3.ipynb
   * lc_extraction_4.ipynb
   * lc_extraction_5.ipynb
   * lc_extraction_6.ipynb

General guide to all notebooks:
1. Requires participant folders organized as `/base_dir/<participant_id>/FSL/`.
2. `base_dir` variable in notebooks needs to be set to dataset root directory, with required brain region masks placed inside here.
3. For each MRI file, the script uses FSL's 'flirt' to register the mask to the MRI image, then applies the mask using fslmaths, thresholds negative values to zero, and calculates the mean intensity inside the masked region using fslstats with flag -M.
4. The output is a CSV file with one row per participant. Column headers indicate the brain region (and which hemisphere) and the corresponding MRI modality.
