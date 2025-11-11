# Amplitude-Modulation

EXP NO: 1	GENERATION AND DETECTION OF AM

AIM:

To generate and detect the amplitude modulation and demodulation u s i n g S C I L A B and to calculate modulation index of AM.

EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

THEORY:

Modulation can be defined as the process by which the characteristics of carrier wave are varied in accordance with the modulating wave (signal). Modulation is performed in a transmitter by a circuit called a modulator.
Need for modulation is as follows:
•	Avoid mixing of signals
•	Reduction in antenna height
•	long distance communication
•	Multiplexing
•	Improve the quality of reception
•	Ease of radiation.
Amplitude Modulation is the process of changing the amplitude of a relatively high frequency carrier signal in proportion with the instantaneous value of the modulating signal. The output waveform contains all the frequencies that make up the AM signal and is used to transport the information through the system. Therefore the shape of the modulated wave is called the AM envelope. With no modulating signal the output waveform is simply the carrier signal. Coefficient of modulation is a term used to describe the amount of amplitude change present in an AM waveform. There are three degrees of modulation available based on value of modulation index.
1)	Under modulation :	m<1, Em < Ec
2)	Critical modulation: m-1, Em = Ec
3)	Over modulation:	m>1, Em > Ec



Note: Keep all the switch faults in off position

Algorithm
1.	Define Parameters
First, define the parameters for your signals:
•	Carrier frequency (fc)
•	Modulating signal frequency (fm)
•	Sampling frequency (Fs)
•	Duration of the signal (T)


2.	Create a time vector based on the sampling frequency and duration.
 
3.	Create Modulating Signal
Define the modulating signal (message signal).

4.	Create Carrier Signal
Define the carrier signal.


5.	Perform Amplitude Modulation
Multiply the carrier signal by the modulating signal plus 1 (to ensure the modulation depth).


6.	Plot the Signals
Visualize the modulating, carrier, and modulated signals.


7.	Demodulate the AM Signal
To demodulate, you can use envelope detection. One way is to rectify the signal and then apply a low-pass filter.

8.	Plot the Demodulated Signal
Visualize the demodulated signal.


9.	Compare Signals
Compare the original modulating signal with the demodulated signal. PROCEDURE
•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Program
```
// Parameters
ac = 18.4;      // Carrier amplitude
am = 9.2;      // Message amplitude
fc = 5800;   // Carrier frequency (Hz)
fm = 580;    // Message frequency (Hz)
fs = 98000;  // Sampling frequency (Hz)

// Time vector
t = 0:1/fs:2/fm;

// Message signal
e1 = am * sin(2 * %pi * fm * t);

// Carrier signal
e2 = ac * sin(2 * %pi * fc * t);

// AM modulated signal
e3 = (ac + e1) .* sin(2 * %pi * fc * t);

// Demodulated signal using Hilbert transform
demod = abs(hilbert(e3)) - ac;

// Plotting
subplot(4,1,1);
plot(t, e1);
xlabel("Time (s)");
ylabel("Amplitude");
title("Message Signal");
xgrid;
subplot(4,1,2);
plot(t, e2);
xlabel("Time (s)");
ylabel("Amplitude");
title("Carrier Signal");
xgrid;
subplot(4,1,3);
plot(t, e3);
xlabel("Time (s)");
ylabel("Amplitude");
title("AM Signal");
xgrid;
subplot(4,1,4);
plot(t, demod);
xlabel("Time (s)");
ylabel("Amplitude");
title("Demodulated Signal");
xgrid;

```


Output Waveform

<img width="1920" height="1080" alt="am 1" src="https://github.com/user-attachments/assets/c538ec79-8ab6-4f61-97d4-c04115940276" />




TABULATION:
![WhatsApp Image 2025-11-11 at 10 48 54_427d7d5a](https://github.com/user-attachments/assets/0413b8d7-749d-40e3-9f6d-46f5b81d76be)

![WhatsApp Image 2025-11-11 at 10 48 56_33693fb3](https://github.com/user-attachments/assets/1dbd8597-4e41-413f-93c7-7a9d5ba6c9e1)


Calculation
1.	ma (Theory) = am/ac =
2.	ma(Practical) = (Emax-Emin)/(Emax+Emin) =


MODEL GRAPH
 <img width="919" height="1290" alt="image" src="https://github.com/user-attachments/assets/55326c5b-7dd5-4873-aaf6-d219bb7c4420" />

 
 


RESULT:
Thus the amplitude modulation and demodulation is experimentally done and the output is verified.
