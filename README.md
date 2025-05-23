# Vibrato Transformation in Choral Singing

This repository contains code and example outputs accompanying the paper:

**"Vibrato Synthesis in Choral Singing via Per-Note Prediction Models"**  
Benjamin Prud’homme  
Department of Computer Science, CUNY Graduate Center  
📄 [PDF of Paper](./Paper.pdf)

## Overview

This project explores the post-hoc injection of pitch-appropriate vibrato into straight-tone choral recordings. Vibrato depth and rate are predicted on a per-note basis using models trained on expressive solo singing (VocalSet), and applied using the WORLD vocoder. The result is a semi-synthetic audio rendering that retains the realism of human performance while enabling expressive variation.

## Contents

### Code Notebooks

- **`GetVocalSetAudioReps.ipynb`**  
  Extracts frame-level pitch, RMS energy, and spectral envelope features from VocalSet recordings.  
  (*Described in Section III-A2.*)

- **`GetVocalSetNoteSegmentations.ipynb`**  
  Performs MIDI-to-audio alignment using DTW to derive note boundaries from VocalSet MIDI files.  
  (*Section III-A3.*)

- **`VibratoModelsPyAMPACT.ipynb`**  
  Trains per-note vibrato depth and rate predictors using features and ground truth from pyAMPACT.  
  (*Section III-B.*)

- **`WorkingVibratoTransformation.ipynb`**  
  Applies the trained models to new recordings (e.g., CSD), synthesizes sinusoidal vibrato, and resynthesizes audio using WORLD.  
  (*Section III-C.*)

### Example Outputs

- **`CSD_ER_alto_4_transformed.wav`**  
  Example transformed output for an alto voice, featured in *Figure 3 (left)*.

- **`CSD_ER_bass_4_transformed.wav`**  
  Example transformed output for a bass voice, showing depth overprediction (*Figure 3, right*).