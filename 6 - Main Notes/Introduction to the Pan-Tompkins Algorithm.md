2025-05-25 21:13

Status #child 

Tags: [[Systems and Signals Analysis]] [[ECG]] [[University Activities]] 

# Introduction to the Pan-Tompkins Algorithm
#### Introduction:
Pan-Tompkins Algorithm is the most common algorithm to detection of QRS complexes in ECG signals. QRS complexes represents ventricular depolarization and is one of the prominent features of the ecg signal, detecting this wave is import for various applications such as determining heart rate and heart rhythm analysis.

The Pan-Tompkins Algorithm for QRS complexes in ECG signals involves several preprocessing steps steps like bandpass filtering, differentiation, squaring, and moving average smoothing to enhance QRS complexes power.

![[Pasted image 20250605171253.png]]

#### Band-Pass Filter:
This filter is used to reduce and unwanted interefereces and maximazing the the QRS energy. The pass-band of the filter is 5-15Hz. This range was especifically chosen to reduce muscle noise and basiline wander, hence smoothing the signal, and remove low frequency noise below 5 Hz such as the T-waves which in this signal are highly elevated.

#### Differentiation and Squaring
The derivative stage plays a crucial role in enhancing the steepnessor slope of the QRS complex, because differentiating a curve enhances rapid changes and sharp edges.

The signal was squared after the derivative stage to ensure that all signal components exhibited positive values. The squaring particularly amplified the higher amplitudes associated with the QRS complex while attenuating other smaller interferences.

To find the QRS peaks we need to merge the peaks resulting from the differentiation stage into a single peak to make it easier for us to detect the QRS peaks.

#### Moving Average Window
A moving average window was applied to the signal to merge the peaks from the previous stage together and cancel sharp edges to facilitate QRS detection. The filter is implemented by convolving the signal with a rectangular window. The window size must be selected appropriately for the filter to work, the size of the window is affected by the sampling frequency and QRS width.

#### Peak Detection


# References
#### Pan-Tompkins Algorithm
- https://medium.com/@cosmicwanderer/pan-tompkins-algorithm-for-detecting-qrs-waves-29c5f2927906

#### Heart rate with Fourier Transform:
- https://kkipngenokoech.medium.com/decoding-heartbeats-unveiling-the-rhythm-with-fourier-analysis-0dddd360dd90