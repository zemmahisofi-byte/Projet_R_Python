# R and Python Project for MAM2DMM - Second year master's internship REHAB -  MAP
------------------------------------------------
# Characterization of cerebellar tremor across standardized upper-limb tasks using smartphone accelerometry Phyhox 

## Author
Sofia Zemmahi

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


### 1.5 Outcome measure 

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