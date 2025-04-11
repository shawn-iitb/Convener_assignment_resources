# Finding Carrier Frequency

Do FFT, there are two spikes at 9.5 KHz and 10.5 KHz
![fft1-big.png](images/fft1-big.png)
![fft1-small.png](images/fft1-small.png)

This implies carrier frequemcy is 10KHz

# Demodulation

* Multiply by sin(2 * pi * Fc * t) or cos(2 * pi * Fc * t)
* A peak will form at 0 Hz and 20KHz
* The 0 Hz peak was higher using sin, so I used sin
![mix1.png](images/mix1.png)

# Low pass

* Apply low pass filter to get actual signal
![low1.png](images/low1.png)

# Noise removal

Repat the last two steps except for two changes:
## Keep only the two peaks of 9.5 KHz and 10.5 KHz by adding two small bandpassed signals
FFT
![ffft1-big.png](images/ffft1-big.png)
![ffft1-small.png](images/ffft1-small.png)
After multiplying with sin
![fmix.png](images/mixf.png)
## Apply band pass filter to remove noise at the end
After low pass
![lowf.png](images/lowf.png)
After another band pass
![ff.png](images/ff.png)

This is the final signal