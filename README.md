# Harmful Brain Activity Classification Project

## Overview
This repository contains the code and documentation for the CS 354N Project Harmful Brain Activity Classification Project. The project was undertaken as part of a Kaggle competition available at [Kaggle Competition - HMS Harmful Brain Activity Classification](https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/).

The goal of this competition was to detect and classify seizures and other types of harmful brain activity using electroencephalography (EEG) signals recorded from critically ill hospital patients. Submissions to this competition aimed to improve electroencephalography pattern classification accuracy, which could have transformative benefits for neurocritical care, epilepsy treatment, and drug development. Advancements in this area could enable faster and more accurate detection of seizures or other brain damage, leading to improved treatments.

## Project Contributors

1. **Krish Agrawal**, Roll Number: 210001034
2. **Pilla Venkata Sekhar**, Roll Number: 210001051
3. **Vishnu V Jaddipal**, Roll Number: 210001078

## Dataset Description

The dataset provided for this competition aims to aid in the detection and classification of seizures and other forms of harmful brain activity using electroencephalography (EEG) data. This task is known to be challenging, even for experts, who may disagree on the correct labels.

### Files
- **train.csv**: Metadata for the training set. Annotators reviewed 50-second EEG samples with matched spectrograms covering a 10-minute window, labeling the central 10 seconds. Metadata includes IDs for EEG recordings, subsamples, label offsets, spectrogram IDs, label IDs, patient IDs, and expert consensus labels.
- **test.csv**: Metadata for the test set. Contains IDs for EEG recordings, spectrograms, and patient IDs. Note that there are no overlapping samples in the test set.
- **sample_submission.csv**: Template for submitting predictions. Includes EEG IDs and target columns for seizure and other types of brain activity.

### Data Directories
- **train_eegs/**: Contains EEG data from overlapping samples. Metadata in `train.csv` is used to select specific annotated subsets. Data was collected at a frequency of 200 samples per second.
- **test_eegs/**: Contains 50 seconds of EEG data for test samples.
- **train_spectrograms/**: Spectrograms assembled from EEG data. Metadata in `train.csv` is used to select specific annotated subsets.
- **test_spectrograms/**: Spectrograms assembled using exactly 10 minutes of EEG data for test samples.
- **example_figures/**: Larger copies of example case images used on the overview tab.

### Target Classes
- **Seizure**: Seizure activity.
- **LPD (Lateralized Periodic Discharges)**: Lateralized periodic discharges.
- **GPD (Generalized Periodic Discharges)**: Generalized periodic discharges.
- **LRDA (Lateralized Rhythmic Delta Activity)**: Lateralized rhythmic delta activity.
- **GRDA (Generalized Rhythmic Delta Activity)**: Generalized rhythmic delta activity.
- **Other**: Other types of brain activity.

### [Kaggle Dataset Link](https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/data)

## Alternate Datasets

### 1. [Brain EEGs Dataset](https://www.kaggle.com/datasets/cdeotte/brain-eegs)
This dataset contains EEG recordings with electrodes ['Fp1', 'T3', 'C3', 'O1', 'Fp2', 'C4', 'T4', 'O2'] for all training data.

### 2. [EEG Spectrogram by Lead ID (Unique)](https://www.kaggle.com/datasets/seanbearden/eeg-spectrogram-by-lead-id-unique)
This dataset is a modification of @cdeotte's notebook to generate spectrograms for raw EEG input. Spectrograms are sliced using the offset (`eeg_label_offset_seconds`) to ensure each sample has a unique EEG spectrogram. Duplicate `eeg_id` were dropped, paired with vote distributions to reduce the sample size to 20,183.

### 3. [Brain Spectrograms Dataset](https://www.kaggle.com/datasets/cdeotte/brain-spectrograms)
This dataset contains spectrograms from Kaggle's HMS - Harmful Brain Activity Classification competition. The file `specs.npy` is a Python dictionary where `spectrogram_id` are the keys. Each value is a NumPy array of shape `(time, 400)`, where each row represents 2 seconds. Each spectrogram has a different length, and the dataset organization is explained in the competition's provided `train.csv` file.

These alternate datasets offer opportunities for exploring EEG data and spectrograms, potentially providing additional insights or approaches for analyzing harmful brain activity.

### Easy inference:
Please use the following colab notebook for easy inference of trained models, using gradio. Please follow the instructions provided in the notebook to load up the pre-trained weights.<br>
[Colab link](https://colab.research.google.com/drive/17GYdTW61Mea4zr5gaj5cifLhkdoBAd4M?usp=sharing)
## Acknowledgements
We would like to express our gratitude to the following individuals: Prof. Aruna Tiwari (Course Coordinator of CS 354N), Teaching and Lab Assistants and to the organizers of the HMS Harmful Brain Activity Classification Kaggle competition for providing the dataset and an opportunity to work on this important problem.
