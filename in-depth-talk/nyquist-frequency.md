# Nyquist frequency

We highly recommend you set the sampling rate to 2khz so for noise spectrum analysis, but without any explanation, we're afraid that only a few people can understand why.

We assume that the readers of this wiki are pilots who have certain flight experience and want to know some details behind the spectrum analysis.

### What does sampling rate mean?

According to the Nyquist-Shannon sampling theorem, the maximum resolvable frequency of a digital signal should be half of the sampling frequency, which is often called the Nyquist frequency.

In other words, assuming we are sampling at a rate of 1khz, then we can "see" the signal frequency in the 0-500hz frequency "window".

### Hey, the motor noise is usually like 450hz for the max!

For a typical 2500KV motor with 4s power, its motor noise frequency range is usually around 0-450hz, which is lower than the Nyquist frequency, which means that theoretically we can see all the frequency of motor noise.

That's right. However, due to the characteristics of the vibration mode of the motor, the vibration of the rotor is often not a pure sine wave, which is accompanied by many harmonic components. The harmonics are the frequency multiples of the fundamental component of the motor noise. This makes it easy for them to break the 500hz "limit" of the Nyquist frequency.

### What about signals higher than the Nyquist frequency?

The frequency of these signals is higher than the Nyquist frequency and is already outside the maximum resolvable frequency. So will they disappear because they are indistinguishable?

Obviously, it won't. Signals higher than the Nyquist frequency will become low-frequency component artifacts again after being sampled and folded back into our "window" to form artifacts. For example, 600hz noise will form a "false frequency" of 400hz. This phenomenon is called aliasing distortion. The following is a very good example.

Note that the aliasing phenomenon does not occur only once. Whenever the signal frequency reaches an integer multiple of the Nyquist frequency, the signal will encounter the upper or lower edge of the "window", and aliasing will occur. For example, as shown in the figure below, note that aliasing also occurs in the 2k sampled spectrum (the second harmonic of motor noise), and the frequency of 1300hz is displayed in the form of 700hz alias. In the 1k sampled frequency spectrum, it is presented as a 300hz alias signal.

Without the use of the 2k sampled spectrum results, even I can hardly give a conclusion on where this frequency comes from.
