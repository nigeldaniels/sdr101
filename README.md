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

