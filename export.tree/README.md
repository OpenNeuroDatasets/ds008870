# Is Geometry the Language of Mathematics or is Space the Language of Both? — fMRI study

Intra-individual, high-density task fMRI dataset (N = 3) from the study *"Is Geometry the Language of
Mathematics or is Space the Language of Both?"* (Ruiz Ibáñez, Gruber, Lindström, Sablé-Meyer &
Klingberg; Department of Neuroscience, Karolinska Institutet).

## Study background
Humans show more accurate and faster responses with regular geometric shapes (e.g. squares, rectangles) than with
irregular ones. This effect is called the *geometric regularity effect*. It has been proposed that this sensitivity to
geometric regularities is specifically linked to mathematical thinking, supported by the anterior intraparietal sulcus (aIPS). The study tested this
against the alternative that geometry is one of many spatial abilities linked to mathematics.

Two online behavioral experiments (N = 150 and N = 200; not part of this dataset) found a robust
geometric regularity effect that did not explain individual differences in mathematical ability. This
fMRI dataset tested neural specificity: each participant performed a geometry localizer, a mathematics
task and three spatial tasks (sequential order, mental rotation, visuospatial working memory), all with
regular vs irregular geometric stimuli, except for the mathematical task. Analyses were done in native space per
participant, to test whether any brain region (in particular within the IPS) is shared exclusively by
geometry and mathematics. All tasks generally activated bilateral aIPS, and no region was exclusive to
geometry and mathematics, pointing to a broad association between mathematics and spatial cognition
rather than a geometry-specific link.

- Preregistration (fMRI study): https://osf.io/gd7xn/
- Materials: https://doi.org/10.5281/zenodo.22744442
- Analysis scripts: https://doi.org/10.5281/zenodo.22798133

## Participants
3 adults (sub-01 to sub-03). Each completed two scanning sessions on the same day (ses-01, ses-02),
each about 75 minutes, with a 15-minute break between sessions and self-paced breaks between runs.
Participants completed an MRI safety screening form and gave written informed consent. The study was
approved by the Stockholm Regional Ethical Review Board (2015/975-31).

## Acquisition
Siemens MAGNETOM Prisma 3T (software XA60), 64-channel head/neck coil, Stockholm University Brain
Imaging Centre (SUBIC).

- **anat**: multi-echo T1-weighted MEMPRAGE, 1 mm isotropic, TR = 2530 ms, TE = 1.69/3.55/5.41/7.27 ms,
  TI = 1100 ms, flip angle 7°, 176 sagittal slices; the RMS combination of the four echoes is provided.
  Acquired in ses-01. Defaced prior to BIDS conversion.
- **func**: T2*-weighted multiband GE-EPI (CMRR), 60 interleaved oblique-axial slices (tilted ~30° from
  AC-PC), 2 mm isotropic, FOV 208 x 208 x 120 mm, TR = 2000 ms, TE = 30 ms, flip angle 76°,
  multiband factor 2, GRAPPA 2, phase encoding A>>P (j-), 150 volumes per run (acquisition time 5 min 20 s).

## Tasks
Stimuli were presented with PsychoPy 2023.2.3. Full task descriptions are in
`task-<label>_bold.json` (TaskDescription) and the conditions in `task-<label>_events.json`.

| task label | task | 
|------------|------|
| `oddball`  | Visual (geometry) localizer: 6-s miniblocks of six 1-s images (regular shapes, irregular shapes, arithmetic formulas, tools, houses, faces), interblock interval 4/6/8 s; button press when the fixation dot turns red 
| `math`     | Number comparison (choose the larger of two numbers in decimal/scientific notation) vs control (choose the vowel); 18-s blocks of three trials 
| `so`       | Sequential order: complete a sequence of five shapes; regular/irregular shapes vs face/tool/house control; 18-s blocks of two trials 
| `rotation` | Mental rotation: pick the correctly rotated target among four options; regular/irregular shapes vs face/tool/house control; 18-s blocks of two trials 
| `wm`       | Visuospatial working memory: five-dot sequences on a 4 x 4 grid, then judge whether a numbered dot matches location and order; regular/irregular sequences vs control; 18-s blocks of two trials 

Task order was fixed across participants:
- ses-01: so, wm, oddball, math, oddball, rotation, math, oddball, rotation, oddball, so, wm, oddball
- ses-02: rotation, math, oddball, so, wm, oddball, wm, so, oddball, rotation, oddball, math, oddball

Runs are numbered per task within each session in acquisition order.

## Events
Stimulus presentation was synchronised with the scanner; onsets are in seconds from the first volume
of each run. Each `*_events.tsv` has one row per trial (`trial_type` = condition, with its duration)
and one row per button press (`trial_type` = `button_press`, duration 0). 

