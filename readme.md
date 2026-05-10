# R and Python Project for MAM2DMM - Second year master's internship REHAB -  MAP
------------------------------------------------
# Characterization of cerebellar tremor across standardized upper-limb tasks using smartphone accelerometry Phyhox 

## 1. Scientific Context 

### 1.1. Background 

A Tremor is an involuntary rhythmic movement involving oscillations or twiching mouvements of one or more body parts (Deuschl et al., 1998).
There are many conditions associated with tremor wich is a frequent symptom in many neurological deseases, particularry cerebellar lesions, but also in functional movement disorders (Deuschl et al., 1998). 

Cerebellar Tremor is an action tremor, meaning that it increases as hand reaches the target. 

Cerebellar tremors are classically characterized by : 
1) low frequency (less than 5 Hz), 
2) high amplitude, 
3) increase as an action approaches a target (Holmes, 1904; Elble, 2003). 

They are often associated with other cerebellar signs, including ataxia, dysmetria, and impaired rapidly alternating movements (Elble, 2003). 

Clinical evaluation of tremor still largly relies on subjectival observations end neurological examination, wich introduce a high degree of subjectivity. The use of inertial sensors, particularly accelerometers embedded in smartphones, may be a good solution to makes it possible to envision an objective, accessible, and reproducible quantification of tremor (Patel et al., 2012; Lipsmeier et al., 2018).

The objective is to quantify tremor frequency during dynamic upper-limb tasks using a reproducible and objective smartphone-based accelerometry measure.

### 1.2. Aim 

The aim of this study is to quantify tremor frequency during standardized dynamic upper-limb tasks using smartphone-based accelerometry, in order to evaluate the feasibility and reproducibility of this method in a clinical setting.

### 1.3. Method

A continuous accelerometric recording was performed using a smartphone fixed on the patient's forearm. Data were collectetd using the Phyphox accelerometer application.
The recording was performed at 100Hz during all sessions in a three dimension (x,y, z). 

The protocol consisted of a sequence of standardized upper-limb tasks:
- rest (hands on knees),
- arms extended forward,
- finger pinch,
- arm elevation,
- finger-to-nose task,
- glass manipulation (grasping and moving),
- drinking,
- filling a glass,
- writing (comparing right end left hand).
- spiral drawing (left then right hand).

Each task was performed for 10 seconds and repeated 3 times times. 
Rest periods were included between tasks.
Data was collected 3 consecutives days to evaluate reproducibility.

To analyze tremor frequency, a Fast Fourier Transform (FFT) was applied to the acceleration signal.
FFT is a method that converts a signal measured over time into a signal expressed in frequency (Oppenheim & Schafer, 2010). It's allows us to see which frequencies are preset in the movement. 
The result is frequency spectrum, where each frequency has an associated amplitude. 
The dominant tremor frequency corresponds to the frequency with the highest amplitude in the spectrum.

### 1.4 Participant
We analyzed the data of one male patient aged 63 years presenting a cerebellar tremor predominantly affecting the left upper limb. 


## 2. Outcome measure 

Dominant tremor frequency (Hz)

Tremor frequency is defined as the number of oscillations per second (Hz) (Deuschl et al., 1998).

It can be estimated in the time domain using the following relation:

$f = \frac{N}{T}$

where:
- *f* is the tremor frequency (Hz),

- *N* is the number of oscillations,

- *T* is the duration of the signal (seconds).

In addition, frequency-domain analysis was performed using Fast Fourier Transform (FFT), which allows identification of the dominant frequency component of the signal (Oppenheim & Schafer, 2010).

The dominant tremor frequency corresponds to the frequency with the highest amplitude in the spectrum (Elble, 2003). 

For each task segment, the dominant tremor frequency was computed from the accelerometer signal.
Each task was repeated three times, and the dominant frequency was calculated for each repetition.
This allowed assessment of:
- differences in tremor frequency between conditions (rest vs drinking),
- and reproducibility of the measurement across repetitions and across recording days.


## 3. Statistical analysis

Statistical analyses were performed using RStudio (R version 2023.06.0+421).

The final dataset was obtained after signal preprocessing and frequency extraction performed in Python. For each recording segment, the following variables were included in the analysis:
- recording day,
- condition (Rest or Task),
- repetition number,
- dominant tremor frequency (Hz),
- RMS amplitude.

The primary variable of interest was dominant tremor frequency, extracted using Fast Fourier Transform (FFT) analysis from accelerometer recordings.

Descriptive statistics were first calculated for dominant tremor frequency, including:
- mean,
- standard deviation (SD),
- median,
- minimum value,
- maximum value.

These analyses were used to verify whether the obtained frequencies remained within the classical cerebellar tremor frequency range described in the literature (approximately 3–5 Hz).

To evaluate intra-day reproducibility, dominant tremor frequency evolution across repetitions was visualized using line plots for each recording day. RMS amplitude evolution across repetitions was also analyzed in order to evaluate tremor intensity modulation during movement.

The coefficient of variation (CV) was calculated for dominant frequency and RMS amplitude to evaluate variability across repeated measurements. Lower CV values were interpreted as better reproducibility.

To evaluate inter-day reproducibility, mean dominant tremor frequencies obtained during Day 1, Day 2 and Day 3 were compared graphically and descriptively.

RMS amplitude values obtained during rest and task conditions were also compared in order to evaluate whether tremor intensity increased during voluntary movement.

Finally, an exploratory Wilcoxon rank-sum test was performed to compare RMS amplitudes between rest and task conditions.

Because this study was designed as an exploratory proof-of-concept feasibility study involving a single patient and a limited number of repetitions, all statistical analyses were considered exploratory rather than confirmatory.

## 4. Results

### 4.1 Intra-day reproducibility of dominant tremor frequency

Dominant tremor frequencies obtained during the three recording days remained within the classical cerebellar tremor frequency range described in the literature (approximately 3–5 Hz).

For Day 1, dominant frequency values remained relatively stable during task repetitions, with frequencies measured at approximately 3.72 Hz and 3.63 Hz during the two completed task repetitions. Greater variability was observed during some rest periods, with frequency values ranging from approximately 3.27 Hz to 4.85 Hz.

During Day 2 and Day 3, dominant tremor frequencies also remained globally stable across repetitions and conditions, supporting acceptable short-term intra-day reproducibility of the measurements.

Coefficient of variation (CV) analyses showed relatively low variability for dominant frequency during task conditions, particularly during Day 1 (CV = 1.73%), suggesting acceptable reproducibility across repeated measurements.



### 4.2 Tremor intensity during rest and task conditions

RMS amplitude analyses demonstrated a markedly different behavior compared with dominant frequency measurements.

Across the three recording days, RMS amplitude values were consistently higher during task conditions than during rest periods.

For Day 1, RMS amplitude reached approximately 0.69 and 0.72 during task repetitions, whereas rest values remained substantially lower overall.

This increase in RMS amplitude during voluntary movement was observed consistently across recording sessions and is clinically coherent with cerebellar tremor physiology, as cerebellar tremor classically increases during action and goal-directed movement.



### 4.3 Inter-day reproducibility

Mean dominant tremor frequencies remained relatively stable between Day 1, Day 2 and Day 3.

Only limited frequency variations were observed between recording days, supporting acceptable inter-day reproducibility of smartphone accelerometer measurements.

Similarly, RMS amplitude patterns remained globally consistent across recording sessions, with systematically higher values during task conditions compared with rest periods.



### 4.4 Exploratory statistical analysis

An exploratory Wilcoxon rank-sum test suggested a difference in RMS amplitude between rest and task conditions (p < 0.001), with substantially higher RMS values observed during voluntary movement.

However, these findings should be interpreted cautiously due to the exploratory proof-of-concept design, the single-patient dataset, and the limited number of repetitions.



### 4.5 Global synthesis of the results

Overall, the analyses performed in this study suggest that smartphone accelerometry combined with FFT analysis can provide coherent measurements of cerebellar tremor characteristics within a proof-of-concept framework.

Across the three recording days, dominant tremor frequencies consistently remained within the classical cerebellar tremor frequency range (approximately 3–5 Hz). Frequency values showed relatively limited variability both between repetitions and between recording days, supporting acceptable intra-day and inter-day reproducibility of the measurements.

In contrast, RMS amplitude values were consistently higher during voluntary movement compared with rest conditions across all recording days, supporting the action-related characteristics of cerebellar tremor.

Taken together, these findings support the feasibility of using smartphone accelerometry to characterize both tremor frequency and tremor intensity in a simple and accessible manner.


## 5. Discussion

The present exploratory study aimed to evaluate whether smartphone accelerometry combined with FFT analysis could provide coherent and reproducible measurements of cerebellar tremor characteristics.

Overall, the obtained results were globally consistent with the clinical characteristics of cerebellar tremor described in the literature. Dominant tremor frequencies remained within the classical cerebellar tremor frequency range (approximately 3–5 Hz) across recording days and repetitions. In addition, RMS amplitude values increased during voluntary movement compared with rest conditions, which is clinically coherent with the action-related nature of cerebellar tremor.

One of the main strengths of this study is the use of a simple and accessible acquisition system based on smartphone accelerometry. Compared with specialized motion analysis systems or dedicated wearable sensors, smartphone-based accelerometry offers several practical advantages, including portability, accessibility, low cost, and ease of use in non-specialized environments.

The reproducibility observed across repetitions and recording days also suggests that smartphone accelerometry combined with FFT analysis may provide sufficiently stable measurements for exploratory tremor characterization.

However, several limitations must be acknowledged.

First, this work was based on a single patient, which prevents any definitive statistical or clinical conclusions. The present study should therefore be considered as a proof-of-concept and feasibility study rather than a confirmatory clinical investigation.

Second, the number of repetitions remained limited, and some recordings may have included movement artefacts, postural adjustments, or residual oscillatory activity that may partially explain the variability observed during some rest periods.

In addition, manual segmentation of task periods may introduce minor variability in the signal processing pipeline. Future studies could improve standardization by implementing automated segmentation methods and more standardized acquisition protocols.

Another important limitation is the absence of comparison with validated clinical accelerometry systems or wearable inertial sensors commonly used in movement analysis research. Future studies could compare smartphone accelerometry measurements with reference devices such as research-grade inertial measurement units (IMUs) or commercially available wearable accelerometers in order to evaluate measurement agreement and external validity.

Future work could also include:
- larger patient cohorts,
- comparison between different tremor disorders,
- longitudinal monitoring,
- task-specific tremor analysis,
- and more advanced signal processing approaches.

It would also be particularly interesting to evaluate whether smartphone accelerometry could differentiate cerebellar tremor from other tremor disorders such as essential tremor or Parkinsonian tremor based on frequency and amplitude characteristics.

Finally, additional analyses could explore other signal-processing features beyond dominant frequency and RMS amplitude, including spectral power distribution, entropy measures, or time-frequency analyses.

Despite these limitations, the present work provides preliminary evidence supporting the feasibility of smartphone-based tremor analysis in a simple and accessible framework.

These findings encourage further investigation of smartphone accelerometry as a potential complementary tool for tremor characterization and monitoring in future larger-scale clinical studies.