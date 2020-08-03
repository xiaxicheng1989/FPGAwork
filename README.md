# Finding parameters for MEMS
The plan is to use FPGA for instant acceleration cancelation.  
We have been testing this method on the gravimeter. The idea is to use FPGA to simulate AI and compare the results with the experimental data to look for difference.  
The difference should reveal bias and scaling factor instability.

## Challenges
FPGA needs to interprete the MEMS data correctly, so that the measurement scale of the MEMS is matched with the interferometer. This is a task requires fine tuning.  
We are trying to measure gravimeter with a vibration on the top. To compensate this signal on AI, the calculated output of FPGA needs to lie within $0$ and $2 \pi$. Because the interferoemter phase corresponding to the gravimeter is a large number, the $2\pi$-conversion of the estimated signal is highly sensitive to the used scaling factor of the MEMS.  

We have tried to visually analyse any compensation effect by setting the integer part of the quotient to be the calculated value using the dynamica range of the interferomter.  

A compensation effect will be demonstrated later in the notebook, however, there is no drastic improvement on the compensation effectivement. This leads us to pursue a more quantitative measure by looking/minimising at the fringe residuals.
