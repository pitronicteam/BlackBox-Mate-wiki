# Sampling flight

In order not to trigger some special tuned algorithm details in BBM kernel code and therefore cause trouble or confusion, we recommend you to do our "sampling flight" to get proper blackbox logs.

There are basically two types of "sampling flight":

* Baseline flight: for PID tunning
* Throttle sweep flight: for filters tunning

### Baseline flight

It's basically Brian's "basement flight". You have to:

* Turn off FF
* Turn off Absolute control
* Turn off I-term roration
* Turn off Vbat sag compensation
* Turn off Thrust Linearization
* Turn off Integral Yaw
* Turn off I-term relax
* Turn off D\_Min
* Turn off Anti-gravity

In all words, you'd better to turn off all the parameters that can dynamically change the PID coefficients.

After that, switch to Angle mode, arm your quads, and hover:

* do some quick move on roll/pitch/yaw axis
* do not kick the wall or anything like that
* fly around 30s and land

Then you finish the baseline flight!

### Throttle sweep flight

Throttle sweep flight is a little bit of dangerous, do at your own risks!

* Keep your normal filter settings
* Do a throttle sweep from 0% to 100% in around 10 secs
* Then do a flip pitch/roll
* Land

Then you finish the throttle sweep flight!
