# R and Python Project for MAM2DMM - Second year master's internship REHAB -  MAP
------------------------------------------------
# Characterization of cerebellar tremor across standardized upper-limb tasks using smartphone accelerometry Phyhox 

## How to run the project

1. Open `Projet_python/main.ipynb` and run all cells to preprocess the accelerometer data and export `all_results.csv`.
2. Open `Projet_RStudio/main.Rmd` and knit the document to generate the statistical analysis.
3. Generated figures are saved in `Projet_python/results/figures/` and statistical outputs are available in `Projet_RStudio/final_data/`.


# 1. Scientific problem

## 1.1. Context

Cerebellar tremor is a movement disorder characterized by low-frequency oscillatory movements that typically increase during voluntary action and goal-directed movement.

Clinical tremor evaluation mainly relies on neurological examination and visual observation. However, these approaches remain partly subjective and may vary according to the examiner and the clinical context.

In recent years, inertial sensors and accelerometers have emerged as promising tools for objective movement quantification. Smartphone accelerometers are particularly interesting because they are:
- inexpensive,
- portable,
- accessible,
- and widely available in clinical and everyday settings.

Fast Fourier Transform (FFT) analysis allows transformation of acceleration signals from the time domain into the frequency domain, making it possible to identify dominant tremor frequencies.

What we are looking for:

To determine whether smartphone accelerometry combined with FFT analysis can provide coherent and reproducible measurements of cerebellar tremor characteristics in a proof-of-concept framework.



## 1.2. Aim

The aim of this study is to evaluate the feasibility of smartphone accelerometry for cerebellar tremor characterization.

More specifically, the objectives are:
- to quantify dominant tremor frequency,
- to evaluate intra-day reproducibility,
- to evaluate inter-day reproducibility,
- and to compare tremor intensity between rest and task conditions.



## 1.3. Method

Acceleration signals were recorded using the smartphone application *PhyPhox*.

The smartphone was attached to the patient’s upper limb during repeated motor tasks.

Recordings were performed over three different days and included:
- rest periods,
- and voluntary movement conditions.

Acceleration was acquired along:
- X axis,
- Y axis,
- Z axis.

Sampling frequency:
- 100 Hz

For each recording:
- acceleration magnitude was computed,
- signal segmentation was performed,
- FFT analysis was applied,
- dominant tremor frequency was extracted,
- RMS amplitude was calculated.



## 1.4. Participant

We analyzed the data of one male patient aged 63 years presenting a cerebellar tremor predominantly affecting the left upper limb. 


## 1.5. Outcome measures

### Dominant tremor frequency

The primary outcome measure was dominant tremor frequency (Hz).

Dominant frequency corresponds to the frequency with the highest amplitude within the FFT spectrum.

Cerebellar tremor is classically associated with low-frequency oscillations between approximately 3 and 5 Hz.



### RMS amplitude

A secondary outcome measure was RMS amplitude (Root Mean Square amplitude).

RMS amplitude reflects tremor intensity rather than tremor frequency.

It was used to compare:
- rest conditions,
- and voluntary movement conditions.



# 2. Python project

## 2.1. Aim

The objective of the Python project was:
- to preprocess accelerometer signals,
- to segment rest and task periods,
- to perform FFT analysis,
- and to extract tremor variables for statistical analysis.



## 2.2. Data organization

### 2.2.1. Raw accelerometer data

For each recording day:
- J1.csv
- J2.csv
- J3.csv

Each file contains:
- timestamp,
- X acceleration,
- Y acceleration,
- Z acceleration.

Sampling frequency:
- 100 Hz

Acceleration unit:
- g


### 2.2.2. Processed data

After preprocessing and FFT analysis, the final dataset was exported as:

- all_results.csv

The file contains:
- Day,
- Phase,
- Condition,
- Repetition,
- Dominant_Frequency_Hz,
- RMS_Amplitude.



## 2.3. Notebook organization

### preprocessing.ipynb

#### Aim

To preprocess raw accelerometer signals and prepare data for frequency analysis.

#### Input

- J1.csv
- J2.csv
- J3.csv

#### Main steps

- Import accelerometer signals,
- Visualization of X, Y and Z signals,
- Computation of acceleration magnitude,
- Manual segmentation of rest and task periods,
- Visualization of segmented signals.

Acceleration magnitude was calculated using:

$$
Magnitude = \sqrt{x^2 + y^2 + z^2}
$$

#### Output

- segmented acceleration signals,
- acceleration magnitude signals,
- cleaned segments for FFT analysis.



### frequency_analysis.ipynb

#### Aim

To extract dominant tremor frequency and RMS amplitude from segmented accelerometer signals.

#### Input

- segmented acceleration signals obtained during preprocessing.

#### Main steps

For each segmented period:
- mean signal removal,
- FFT computation,
- extraction of positive frequencies,
- analysis of frequencies between 3 and 5 Hz,
- dominant frequency identification,
- RMS amplitude computation.

#### Output

- dominant tremor frequency values,
- RMS amplitude values,
- all_results.csv exported for statistical analysis.



# 3. RStudio project

All analyses were performed in a proof-of-concept framework and should not be interpreted as clinical validation.

## 3.1. Aim

The objective of the RStudio project was to evaluate:
- intra-day reproducibility,
- inter-day reproducibility,
- and tremor intensity modulation during action.



## 3.2. Data organization

### Input file

- all_results.csv

### Columns

- Day : Recording day (D1, D2, D3)
- Phase : Rest or task phase
- Condition : Rest or Task
- Repetition : Repetition number
- Dominant_Frequency_Hz : Dominant tremor frequency extracted from FFT analysis
- RMS_Amplitude : RMS amplitude value



## 3.3. Script organization

### 3.3.1. Descriptive statistics

#### Aim

To describe dominant tremor frequency distributions across:
- repetitions,
- recording days,
- and experimental conditions.

#### Input

- all_results.csv

#### Calculated variables

- mean frequency,
- standard deviation (SD),
- median frequency,
- minimum frequency,
- maximum frequency.

#### Output

Summary tables describing tremor frequency distributions for:
- Day 1,
- Day 2,
- Day 3,
- and all recording days combined.



### 3.3.2. Intra-day reproducibility analysis

#### Aim

To evaluate the stability of dominant tremor frequency across repetitions within the same recording day.

#### Input

- all_results.csv

#### Main analyses

- Line plots of dominant frequency across repetitions,
- Visualization of rest and task conditions,
- Coefficient of variation (CV) calculation.

#### Calculation

$$
CV = \frac{SD}{Mean} \times 100
$$

where:
- SD is the standard deviation,
- Mean is the average dominant frequency.

#### Output

- frequency evolution plots,
- intra-day variability measurements,
- CV tables.



### 3.3.3. Inter-day reproducibility analysis

#### Aim

To evaluate the consistency of dominant tremor frequency measurements across recording days.

#### Input

- all_results.csv

#### Main analyses

- Comparison of dominant frequencies between D1, D2 and D3,
- Mean frequency visualization across days,
- Global variability analysis.

#### Output

- inter-day comparison plots,
- inter-day summary statistics,
- exploratory reproducibility assessment.



### 3.3.4. RMS amplitude analysis

#### Aim

To compare tremor intensity between:
- rest conditions,
- and voluntary movement conditions.

#### Input

- all_results.csv

#### Main analyses

- RMS amplitude visualization,
- Mean RMS comparison,
- Exploratory statistical comparison using Wilcoxon rank-sum test.

#### Output

- RMS amplitude plots,
- RMS summary tables,
- exploratory statistical comparison.



## 3.4. Interpretation framework

Because this study included:
- a single patient,
- a limited number of repetitions,
- and exploratory analyses,

the objective was not to establish definitive clinical conclusions but rather to evaluate the feasibility and coherence of smartphone-based tremor analysis.



## 3.5. Global interpretation

Overall, dominant tremor frequencies remained within the classical cerebellar tremor range (approximately 3–5 Hz) across repetitions and recording days.

Frequency measurements showed relatively limited variability, suggesting acceptable intra-day and inter-day reproducibility.

RMS amplitude values were consistently higher during voluntary movement conditions compared with rest conditions, which is clinically coherent with cerebellar tremor physiology.

Together, these observations support the feasibility of smartphone accelerometry combined with FFT analysis for exploratory tremor characterization.

---

# 4. Discussion

This proof-of-concept study suggests that smartphone accelerometry may provide accessible and clinically coherent measurements of cerebellar tremor characteristics.

One of the main strengths of this approach is the use of widely available technology that may potentially simplify quantitative tremor assessment in clinical practice.

However, several limitations must be acknowledged:
- single-patient dataset,
- limited number of repetitions,
- manual signal segmentation,
- absence of comparison with validated motion capture systems,
- possible movement artefacts.

Future studies should therefore include:
- larger populations,
- additional tremor disorders,
- standardized acquisition protocols,
- comparison with validated accelerometers,
- blinded analyses,
- multicentric validation studies.



# 5. Conclusion

This exploratory work supports the feasibility of smartphone accelerometry combined with FFT analysis for cerebellar tremor characterization.

Dominant tremor frequency measurements remained coherent with classical cerebellar tremor physiology and demonstrated acceptable reproducibility across repetitions and recording days.

Although larger validation studies remain necessary, these preliminary findings suggest potential clinical interest for accessible smartphone-based tremor analysis tools.



# 6. References

1. Deuschl G, Bain P, Brin M. Consensus statement of the Movement Disorder Society on Tremor. Movement Disorders. 1998.

2. Elble RJ. Tremor: clinical features, pathophysiology, and treatment. Neurologic Clinics. 2009.

3. Oppenheim AV, Schafer RW. Discrete-Time Signal Processing. Pearson. 2010.

4. Patel S et al. A review of wearable sensors and systems with application in rehabilitation. Journal of NeuroEngineering and Rehabilitation. 2012.

5. Lipsmeier F et al. Evaluation of smartphone-based testing to generate exploratory outcome measures in Parkinson’s disease. Movement Disorders. 2018.