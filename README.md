# Analog Input Noise Characertization
 Characterize noise of Analog input signals captured using an NI hardware ADC using Power Spectral Denisty and Cumulative Power Spectrum
 
Noise Characterization of AI chain - useful to characterize sensor noise coming into the main control loop. Designed for the myRIO and cRIO, extends to other RIO based systems.

**FPGA:** Samples code at a variable rate, applies a settable low-pass filter in the Analog Input (AI) chain. Also has ability to output a specified AO value or 100 times the AI value after the low-pass filter to view on an oscilloscope.

**RT-target:** Reads data from FPGA at a specified loop rate for transfer to Host-PC over TCP/IP for analysis. Also provides a UI to modify FPGA controls as needed. 

**Host-PC:** Reads data from the RT-target and performs spectral analysis - Power Spectral Density and Cumulative Power Spectrum and plots them in the UI.

**Run RT Code and then PC code.** Open AI_NoiseCharacterization.lvproj and then Run RT_AIChar_v2.vi. After the RT_AIChar_v2.vi is running, also run the PC_AIChar_v2.vi. The Histogram and PSD analysis is in the PC_AIChar VI. You can select various options for AI sampling in the RT_AIChar VI. Select the correct Target to set the IP address for the STM messaging server.

![RT-target front panel](ReadME_images/RT_UI.png "RT-target front panel")

![Host-PC front panel](ReadME_images/Host-PC_UI.png "Host-PC front panel")

To run this in LabVIEW, download and install the following packages from [VI Package Manager](http://www.ni.com/tutorial/54770/en/):
1. Simple Messagine Library (STM) - [vipm://ni_lib_stm/?repo_url=http:/ftp.ni.com/evaluation/labview/lvtn/vipm](vipm://ni_lib_stm/?repo_url=http:/ftp.ni.com/evaluation/labview/lvtn/vipm)
2. Structured Error Handler (SEH) - [vipm://ni_lib_seh/?repo_url=http:/ftp.ni.com/evaluation/labview/lvtn/vipm](vipm://ni_lib_seh/?repo_url=http:/ftp.ni.com/evaluation/labview/lvtn/vipm)
