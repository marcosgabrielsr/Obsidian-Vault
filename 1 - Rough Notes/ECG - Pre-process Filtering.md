2025-05-02 09:47

Status: #teen  

Tags: [[Systems and Signals Analysis]] [[ECG]]

# ECG - Pre-process Filtering

#### Introduction:

Filters are applied to clean the ECG signals. There are several types of filters, and knowing which one to choose is crucial.The contamination on ECG signal comes from a variety of sources within and outside of patient's bodies. 

The ECG frequencies typically fall in the range of 0.5 to 150 Hz (in some cases the max frequency is 40 Hz) , and filters designed to remove noise outside of this range are relatively straightforward. The process gets trickier when the interference overlaps with the ECG frequency range.

There are many types of filters, but four of the most commonly used are low-pass, high-pass, power line, and anti-aliasing filters.

#### Low-Pass Filters:
- **Description:** Allow lower-frequency signals to pass through and block any frequencies above a certain threshold, which is typically set at 150 Hz because the clinically relevant info in the ECG falls below that, but, can set at 40 Hz in some cases. This type of filtering will smooth out the ECG signal, easing the reader's task for interpreting findings in the lower-frequency range, like arrhythmias and QRS intervals. But it may also have an impact on the amplitude of the signal, potentially affecting the diagnosis of conditions that rely on QRS amplitude, such as hypertrophic cardiomyopathies. The lower the cutoff employed for the low-pass filter, the greater the distortion of the amplitude.

#### High-Pass Filters:
- **Description:** Another type of contamination you might see on the ECG is baseline wander. This is often due to the patient's breathing. If there's not a good electrical connection, this would present as a rolling of the signal on the baseline. Respiration artifacts come in below 0.5 Hz and a clinician can address them with the use of high-pass filters, which block frequencies below a specific cut point. This type of linear filter, however, can come with both phase and amplitude distortion on the low end of the ECG frequency range. This can result, for example, in some of the energy from a high-frequency component like the QRS bleeding into and distorting the ST segment, which may lead to false-positive findings for conditions including ischemia or myocardial infarction. Using a zero-phase delay (ZPD) filter will help mitigate the effects of phase distortion.

#### Power-Line Filters:
- **Description:** 

# References

#### Introduction to the ECG
- https://medium.com/@cosmicwanderer/introduction-to-the-ecg-42d494ddaa94

#### Pan-Tompkins Algorithm
- https://medium.com/@cosmicwanderer/pan-tompkins-algorithm-for-detecting-qrs-waves-29c5f2927906

#### Methods to filter ECG dataset:
- https://www.gehealthcare.com/insights/article/a-guide-to-ecg-signal-filtering
- https://pmc.ncbi.nlm.nih.gov/articles/PMC7067057/#:~:text=In%20continuous%20monitoring%2C%20ECG%20signal
- https://www.researchgate.net/figure/Common-types-of-noise-in-ECG-recordings-a-Baseline-wander-b-50-Hz-power-line_fig2_221923119
#### How to visualizate ECG signals:
- https://ecgwaves.com/topic/systematic-clinical-ecg-interpretation-review-guide/

#### How to apply filters with Python
- https://www.youtube.com/watch?v=Aht4letBAmA&t=233s