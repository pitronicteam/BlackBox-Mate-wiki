# Noise Analysis

The PID controller relies on gyro data. So if the real motion signal of the drone is submerged in noise, the PID controller might perform poorly which makes unstable control and even cause the drone to lose control completely and crash.

You would better do a throttle sweep sampling flight according to our [Sampling flight wiki](../quick-guide/sampling-flight.md) before the analysis.

In addition, I wanna say that noise analysis is not offered as a universal technique capable of solving all problems, but rather as an adjunct to the classical methods already well known and tried. We assume that the readers of this wiki are pilots who have certain flight experience but only know little about noise analysis.

### The composition of noise

The noise on our drones often consists of several different parts, like:

* electronic sensor noise (including voltage spikes from ESCs, gyro sensor's random noise, radio frequency interference from video signal lines for example, etc),
* resonances in frame/props/other setups,
* motor vibrations

In BBM, we offer the PSD (Power Spectral Density) plots to analyze the power of the noise of a drone.



Noted that our PSD plots are just like noise plots in Plasmatree-analyzer which are non-cumulative, which means the result of the plots is not related to the flight time length.

* The X-axis is throttle from 0-100%.
* The Y-axis is the frequency in Hz, ranging from 0Hz to Nyquist frequency (depends on your sampling frequency). For more details about Nyquist frequency, you can check our wiki here: [Nyquist frequency](../in-depth-talk/nyquist-frequency.md)
* The Z-axis is the power value (normalize by sampling frequency, see FFT, Power Spectrum and PSD for more details), rendered with a colormap called by `magma`.
* The colour-grading is on a logarithmic scale to improve details (`10 x log10(PSD)`,default is -40 \~ +10dbm)
* If you set your blackbox debug mode to `GYRO_SCALED`then BBM will calculate and plot raw gyro data PSD result which is the prefiltered gyro signal, this is quite useful if you wanna analyze your noise from the scratch

### Example

Let's grab



