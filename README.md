# sdr101
first sdr experimets using the HackRF and GRC 


#lesson1 - basic FM radio  
create osmocom source 
  - Sample Rate (sps): <samp_rate> 10M - this will define the sample rate of the sdr
  - Ch0: Frequency   : <center_freq> - This is set to the middle of the fm band 97.9mhz or 97.9e6 
  - Ch0: RF Gain     :0 -  this sets the power of the recive amp set to 0 for safety 

Create WXGUI FFT sink - does fft analysis on input and graphs 
  - Sample Rate   : <samp_rate> 10M - this will define the sample rate of the sdr
  - Baseband freq : <center_freq> - This will be the center of the graph 
  - Average       : on - makes the graph easier to read

  now is probably a good time to connect the blocks and execute 

Create Multiply block - shift a frequency to center(multiplies 2 signals) 

Create variable <channel_freq> 
  -Value : 96.5 mhz or 96.5e6 

Create Signal Source  - gotta remember why this actually works 
  - Frequency - <center_freq> - <channel_freq>

This is a good time to test with another fft block if you want 

Create low pass filter - this is the first step in demodulating (I still dont understand this part) 
  - sample rate: <samp_rate>
  - cutoff freq: 75e3 or 75khz 
  - transition width: 25e3 or 25khz
  - Decimation int(samp_rate/channel_width) 

Create Rational resampler ( or this part) 
  - interpolation:12 
  - Decimation:5

Create FM reciver block 
 - Quadrature Rate: 480e3 or 48khz - standard sample rate for audio 
 - Audio Decimation:10
 
Create audo sink - last block this just inputs to sound card 
 -sample rate: 480e2 or 48khz

