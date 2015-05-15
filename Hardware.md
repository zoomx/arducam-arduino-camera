# Hardware #
ArduCAM shield hardware integrates all the necessary components to interface with camera modules. User only need a extra support camera modules and a TF/SD card to start image capture.

The shield provide the following features:

Dedicate DigtalVideoPort Camera Module Interface
  * 3.2” TFT Color LCD Screen(a)
  * Build-in 3Mbit FIFO Memory
  * TF/SD Card Reader with LED indicator
  * 6 Input/Output Software Programmable GPIOs expander
  * 4 Pin Headers which well mated with UNO board
Note: (a) Model ArduCAM-F doesn’t not include a 3.2” LCD screen

## Camera Interface ##

CMOS image sensor interface divided into two catalogs, one is DVPDigitalVideoPort interface, the other is MIPI Mobile Industry Processor Interface. The main difference between DVP and MIPI is that DVP is parallel interface and the MIPI interface is high speed differential serial interface. MIPI interface provide higher data band width than DVP interface and support higher resolution and frame rate. Because the complexity and need additional hardware of MIPI interface, we only discuss DVP interface here.

For a standard DVP image sensor you will find the following signals:

  * SCL: I2C compatible clock signal for sensor registers configuration
  * SDA: I2C compatible data signal for sensor registers configuration
  * XCLK: clock input to the sensor
  * PCLK: clock output from the sensor,
  * HREF: Line valid signal
  * VSYNC: Frame valid signal
  * Data[N-1..0]: Data output from the sensor, N is the internal ADC bit width.

ArduCAM shield provide a DVP interface which support wide range of camera modules from 0.3MP to 5MP. The camera modules should line up with the shield based on Pin1 shown in the Figure 1 and Table 1 provide camera interface pin out on the shield.

Figure1
![http://www.arducam.com/wp-content/uploads/2013/06/CAM_Pin_out.jpg](http://www.arducam.com/wp-content/uploads/2013/06/CAM_Pin_out.jpg)


Table 1
|**Pin**|**Signal**|**Pin**|**Signal**|
|:------|:---------|:------|:---------|
| 1	| +3.3V| 2	| GND|
| 3	| SCL	| 4	| SDA|
| 5	| VSYNC| 6	| HREF|
| 7	| PCLK	| 8	| XCLK|
| 9	| D7	| 10	| D6|
| 11	| D5	| 12	| D4|
| 13	| D3	| 14	| D2|
| 15	| D1	| 16	| D0|



## ArduChip ##

The ArduCAM shield includes a ArduChip which handle complex timing between MCU and LCD, Camera, FIFO. It exports a standard 8051 parallel interface shown in Table 2 and can be interfaced with wide range of micro-controller. MCU control the shield through a set of ArduChip internal registers shown in Table 3.

To be continue...