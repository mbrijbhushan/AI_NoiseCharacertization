# AI_NoiseCharacertization
 Characterize noise of AI signals using Power Spectral Denisty and Cumulative Power Spectrum
 
Designed for the myRIO, extends to other RIO based systems such as cRIO.

FPGA: Samples code at a variable rate, applies a settable low-pass filter in the Analog Input (AI) chain. Also has ability to output a specified AO value or 100 times the AI value after the low-pass filter to view on an oscilloscope.

RT-target: Reads data from FPGA at a specified loop rate for transfer to Host-PC over TCP/IP for analysis. Also provides a UI to modify FPGA controls as needed. 

Host-PC: Reads data from the RT-target and performs spectral analysis - Power Spectral Density and Cumulative Power Spectrum and plots them in the UI.

To run this in LabVIEW, you will need to dowload and install the following packages from [VI Package Manager](http://www.ni.com/tutorial/54770/en/):
1. Simple Messagine Library (STM) - [vipm://ni_lib_stm/?repo_url=http:/ftp.ni.com/evaluation/labview/lvtn/vipm](vipm://ni_lib_stm/?repo_url=http:/ftp.ni.com/evaluation/labview/lvtn/vipm)
2. Structured Error Handler (SEH) - [vipm://ni_lib_seh/?repo_url=http:/ftp.ni.com/evaluation/labview/lvtn/vipm](vipm://ni_lib_seh/?repo_url=http:/ftp.ni.com/evaluation/labview/lvtn/vipm)

Run RT Code and then PC code. Open AIChar.lvproj and then Run RT_AIChar_v2.viand after it is running, also run the PC_AIChar_v2.vi. The Histogram and PSD is in the PC_AIChar VI. You can select various options for AI sampling in the RT_AIChar VI.

