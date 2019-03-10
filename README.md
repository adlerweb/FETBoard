# FETBoard

FETBoard is a Shield that connects to either an NodeMCU or Arduino Pro Mini. It breaks out 7 Inputs and 5 Outputs. Two inputs can be changed into outputs via jumpers. Inputs use a resistor to provide some level of protection. Outputs use a SI2302DS which is rated at 2.4A. Due to the losses involved I would suggest to stay below 1A per channel. On the Pro Mini Pins used for SPI where kept clear to allow for interfacing additional modules.

## Warnings

The board was a quick'n'dirty solution to get some of my connections done. It was created somewhere around 2am, so there is a lot of stuff that could be done better.

* There are no Pull-Ups/Down for either In- or Output. Especially outputs might not behave as expected if your code doesn't drive the outputs or the controller crashes
* Wiring is a mess, don't even try to find any logic here

## Things required

* NodeMCU or Arduino Pro Mini (duh!)
* Enough female pin headers to accommodate the controller mentioned. Use the spring loaded type, turned ones won't fit the controllers pins.
* Any 5.08mm Screw Terminals
* 7 x SI2302DS
* 7 x Resistor for SI2302DS - something between 500Ω and 5kΩ should be OK. Lower values lead to less losses when using PWM, higher ones don't stress the controller as much.
* 7 x Resistor for inputs - Anything you're comfortable with. Some 10s of kΩ should be a good compromise

## Pinout

| Side   | Pin | NodeMCU | Pro Mini |
|--------|-----|---------|----------|
| Input  | 1 (Left)   | GND     | GND      |
| Input  | 2   | D6 (JP1)| D7 (JP1) |
| Input  | 3   | D5 (JP2)| D4 (JP2) |
| Input  | 4   | N/C     | A3       |
| Input  | 5   | 3       | A2       |
| Input  | 6   | D8      | A1       |
| Input  | 7   | D7      | A0       |
| Output | 8   | D0      | D2       |
| Output | 1 (Left)  | Vin     | RAW      |
| Output | 2   | D6 (JP1)| D7 (JP1) |
| Output | 3   | D5 (JP2)| D4 (JP2) |
| Output | 4   | N/C     | D9       |
| Output | 5   | D4      | D8       |
| Output | 6   | D3      | D6       |
| Output | 7   | D2      | D5       |
| Output | 8   | D1      | D3       |

