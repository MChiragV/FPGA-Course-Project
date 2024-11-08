# FPGA-Course-Project
Implementation of compression on images
## Reference Github Link
https://gitlab.com/libtiff/libtiff/-/blob/master/tools/tiffcp.c


### Simulation:
![image](https://github.com/user-attachments/assets/64862aab-8f1e-495a-8230-11d3a8f0922e)

### Steps to export:
1. Open ILA.
2. Add the signal `ila_start` as a trigger to a rising edge. This signal is a pulse which only goes high for 1 clock cycle when we start reading the array.
3. Run the trigger.
4. You will see the trigger in the centre of the window, which is at 512th sample (1024 depth of ILA). So the array will start at 512th sample and get circled back until it reaches the centre.
5. If we can set the trigger at the 0th sample, there won't be any circle. To do this, use the following command in the Tcl Console:
   ```
   set_property CONTROL.TRIGGER_POSITION 0 [get_hw_ilas hw_ila_1]
   ```
6. You can now export this array as a csv file.
![image](https://github.com/user-attachments/assets/97332443-a623-42e3-b729-51ba0a7ae870)

### Compressed output example:
![Screenshot 2024-10-31 145950](https://github.com/user-attachments/assets/68f61abf-a969-4381-ae8b-37375c739f50)

