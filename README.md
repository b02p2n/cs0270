java c
Digital Biosignal Processing
MATLAB Laboratory 3
An Electroencephalography (EEG) signal has been recorded from the scalp of a healthy individual during rest at the sampling frequency of 512 Hz for 15 s. The electrode location of the recording in the standard 10-20 system was Cz. The EEG represents the electrical activity of the brain and it is commonly analyzed in the frequency domain. Relevant frequency bands are categorized as Delta (0.5 ≤ f ≤ 4 Hz), Theta (4 ≤ f ≤ 8 Hz), Alpha (8 ≤ f ≤ 13 Hz), Beta (13 ≤ f ≤ 30 Hz), and Gamma (30≤ f ≤ 42 Hz). An example of some of these signal components is reported in the figure below. The relative power of the signal at the different bands indicates different brain states.

Study the short Matlab script. provided and understand the meaning of the parameters. Use the Matlab script. to estimate the power spectral density (PSD) of the signal. The PSD is simply obtained from the Discrete Fourier Transform. (DFT), as follows (see slides Lecture 3 and the provided Matlab script):

From the PSD, estimate the percent of power in the Delta, Theta, Alpha, Beta, and Gamma bands. The percent of power in a given band is computed by the area of the PSD in the band relative to the total area, as follows:

Where k1 and k1 are the discrete frequencies corresponding to the band to be analyzed and the denominator expresses the sum over the entire bandwidth (positive frequency values only).
In your report, please provide the following:- Plot of the PSDs of the signal obtained by analysing signal intervals of 1 s, 5 s, and 15 s. Comment on the differences between these PSDs. [50%]- Report the percentage of power in the Del代 写Digital Biosignal Processing MATLAB Laboratory 3Matlab
代做程序编程语言ta, Theta, Alpha, Beta, and Gamma bands obtained from the PSD computed from signal intervals of 1 s, 5 s, and 15 s (a table is suggested). Comment on the results. [50%]PLEASE NOTICE: The report is limited to one A4 page, including all graphs and comments.
% Third tutorial
clear all
close all
clc
% Signal loading
load('EEG.mat');
% Sampling frequency
fsamp = 512;
% Select duration to analyze
Duration = 1; % Duration in seconds (max 15 seconds)
Duration = round(Duration*fsamp);
EEG = EEG(1:Duration);
% Signal duration in samples
L = length(EEG);
% Plot the EEG signal
time_ax = [0:L-1]./fs
figure(1)
plot(time_ax, EEG);
xlabel('Time (s)')
title(['EEG signal'])
ylabel('Amplitude EEG (Arbitrary Units)')
% Compute DFT
X1 = fft( EEG - mean(EEG) );
% Compute PSD (power spectral density)and adjust
% frequency axis according to Matlab notation
PSD1 = fftshift(abs(X1).^2)/L;
% Build the frequency axis in radiants
freq_a_rad = [-pi+pi/L:2*pi/L:pi-pi/L];
% Convert the frequency axis in Hz
freq_a_Hz = freq_a_rad./(2*pi).*fs
% Plot the PSD with frequencies in radiants and Hz
figure(2), subplot(2,1,1), plot(freq_a_rad,PSD1);
xlabel('Frequency (radians)')
title('Power Spectral Density of EEG')
ylabel('PSD (Arbitrary Units)')
figure(2), subplot(2,1,2), plot(freq_a_Hz,PSD1);
xlabel('Frequency (Hz)')
title('Power Spectral Density of EEG')
ylabel('PSD (Arbitrary Units)')
%% Compute the percentage of power in different subbands
[Here please complete with instructions for computing the relative power in the frequency bands.]


         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
