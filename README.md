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
clc;
clear;
close;
Am = 8.8;          // Message amplitude
Ac = 17.6;         // Carrier amplitude
Fm = 540;          // Message frequency
Fc = 5400;         // Carrier frequency
Fs = 54000;        // Sampling frequency

t = 0:1/Fs:0.005;  // 5 ms duration (can increase if needed)

//// Message signal
m = Am * sin(2 * %pi * Fm * t);

//// Carrier signal
c = Ac * sin(2 * %pi * Fc * t);

//// AM modulated signal
s = Ac * (1 + (Am/Ac) * sin(2 * %pi * Fm * t)) .* sin(2 * %pi * Fc * t);
subplot(3,1,1)
plot(t, m)
title('Message Signal')
xlabel('Time (s)')
ylabel('Amplitude')
xgrid()
subplot(3,1,2)
plot(t, c)
title('Carrier Signal')
xlabel('Time (s)')
ylabel('Amplitude')
xgrid()
subplot(3,1,3)
plot(t, s)
title('AM Modulated Signal')
xlabel('Time (s)')
ylabel('Amplitude')
xgrid()
disp("   Time(s)        Message(V)        Carrier(V)        Modulated(V)");
for i=1:10:length(t) // Display every 10th sample for brevity
    mprintf("%10.6f    %10.4f    %10.4f    %10.4f\n", t(i), m(i), c(i), s(i));
end



Output Waveform
<img width="759" height="728" alt="Screenshot 2025-10-30 083522" src="https://github.com/user-attachments/assets/be9c9d14-e353-4df1-9919-41aa65cb0725" />





TABULATION:
![WhatsApp Image 2025-11-27 at 21 14 32_56aac963](https://github.com/user-attachments/assets/d3ffea6d-9d0c-4c4a-957a-a0ff05dbf02a)


Calculation
1.	ma (Theory) = am/ac =8.8/17.6=0.5
2.	ma(Practical) = (Emax-Emin)/(Emax+Emin) =(26.4-8.8)/(26.4+8.8)=0.5


MODEL GRAPH
 <img width="919" height="1290" alt="image" src="https://github.com/user-attachments/assets/55326c5b-7dd5-4873-aaf6-d219bb7c4420" />

 
 


RESULT:
Thus the amplitude modulation and demodulation is experimentally done and the output is verified.
