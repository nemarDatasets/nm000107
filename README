# wrist: Wrist Movement Control from EMG

## Overview

**Dataset**: wrist - Wrist posture and movement from wrist-based surface electromyography
**Task**: 1D continuous cursor control via wrist flexion/extension
**Participants**: 100 subjects
**Sessions**: 100 total (1 per subject)
**Publication**: Kaifosh et al., 2025 - "A generic non-invasive neuromotor interface for human-computer interaction" (Nature)

### Purpose

This dataset captures wrist-based sEMG signals during wrist movements for continuous cursor control. Motion capture provides ground-truth wrist angles. The goal is to enable gesture-free control through wrist posture alone, demonstrating sEMG's ability to decode motor intent before visible movement occurs.

## Dataset Details

### Participants
- **Sample size**: 100 participants
- **Demographics**: Not available (marked as n/a)
- **Recording side**: Dominant wrist
- **Sessions**: 1 per participant

### Hardware
- **Device**: sEMG-RD (single wristband)
- **Channels**: 16 (EMG0-EMG15)
- **Sampling rate**: 2000 Hz
- **Reference**: Bipolar differential
- **Ground truth**: Motion capture wrist angles

### Recording Protocol
1. Participant wears sEMG-RD on dominant wrist
2. Motion capture tracks wrist angles in real-time
3. Participant controls horizontal cursor position with wrist flexion/extension
4. Target acquisition task: Navigate to targets and hold for 500ms

## Data Contents

### Files per Session
```
sub-XXX/ses-XXX/emg/
├── sub-XXX_ses-XXX_task-wrist_emg.edf
├── sub-XXX_ses-XXX_task-wrist_emg.json
├── sub-XXX_ses-XXX_task-wrist_channels.tsv
├── sub-XXX_ses-XXX_task-wrist_events.tsv
└── sub-XXX_ses-XXX_electrodes.tsv
```

### Events
- **Stage boundaries**: Task phases and movement trials

### Coordinate System
Single coordinate system at root (dominant wrist, percent units, no decimals)

## Signal Processing

**Note**: This dataset has significant data quality issues:
- Duplicate timestamps found in many sessions (up to 88% duplicates)
- Irregular sampling requiring resampling (up to 916% deviation)
- Post-processing: Duplicate removal followed by resampling to regular 2000 Hz

## Baseline Performance

### Published Results (Kaifosh et al., 2025)

**Offline Evaluation**:
- Wrist angle velocity error: <13°/s
- Error decreases with more training participants

**Closed-loop Performance** (n=17 naive test users):
- **Target acquisition time**: Median 1.51s (sEMG decoder)
- **Dial-in time**: Time to re-acquire after premature exit
- **Learning effects**: Improvement from practice to evaluation blocks

**Comparison**:
- Motion capture ground truth: 0.96s
- MacBook trackpad: 0.68s
- sEMG decoder: 1.51s (2.2× slower than trackpad)

**Model architecture**: MPF features + LSTM

## Key Findings
- **Predictive signals**: sEMG precedes movement by tens of milliseconds
- **Generic models work**: Out-of-the-box cross-user generalization
- **Continuous control**: Demonstrates feasibility of gesture-free interfaces
- **Room for improvement**: Performance gap vs traditional inputs

## Use Cases
- **Continuous control**: Cursor/pointer movement
- **AR/VR navigation**: Hands-free interface
- **Low-effort control**: Minimal visible movement required
- **Predictive decoding**: Intent detection before motion completion

## Known Limitations
- Single degree of freedom (1D control only)
- Single wrist (dominant hand)
- Duplicate timestamps (data quality issue)
- Performance below traditional inputs
- Extension to 2D control not demonstrated

## Citation
```
Kaifosh, P., Reardon, T.R., & CTRL-labs at Reality Labs. (2025).
A generic non-invasive neuromotor interface for human-computer interaction.
Nature, 586, https://doi.org/10.1038/s41586-025-09255-w
```

## Data Curator
**Yahya Shirazi**
SCCN (Swartz Center for Computational Neuroscience)
INC (Institute for Neural Computation)
University of California San Diego

## Version History
**v1.0** (2025-10-01): Initial BIDS conversion

---
**BIDS Version**: 1.11 | **EMG-BIDS**: BEP-042 | **Updated**: Oct 1, 2025
