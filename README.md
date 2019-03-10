# FETBoard

FETBoard is a Shield that connects to either an NodeMCU or Arduino Pro Mini. It breaks out 7 Inputs and 5 Outputs. Two inputs can be changed into outputs via jumpers. Inputs use a resistor to provide some level of protection. Outputs use a SI2302DS which is rated at 2.4A. Due to the losses involved I would suggest to stay below 1A per channel. On the Pro Mini Pins used for SPI where kept clear to allow for interfacing additional modules.

## Warnings

The board was a quick'n'dirty solution to get some of my connections done. It was created somewhere around 2am, so there is a lot of stuff that could be done better.

* There are no Pull-Ups/Down for either In- or Output. Especially outputs might not behave as expected if your code doesn't drive the outputs or the controller crashes
* Wiring is a mess, don't even try to find any logic here

## Things required

* NodeMCU or Arduino Pro Mini (duh!)
* Enough female pin headers to accommodate the controller mentioned. Use the spring loaded type, turned ones won't fit the controllers pins.
* Any 3mm Screw Terminals
* 7 x SI2302DS
* 7 x Resistor for SI2302DS - something between 500Ω and 5kΩ should be OK. Lower values lead to less losses when using PWM, higher ones don't stress the controller as much.
* 7 x Resistor for inputs - Anything you're comfortable with. Some 10s of kΩ should be a good compromise

# Known bugs
* NodeMCU-footprint is incorrect. Only plug in the right side (D0, etc). You'll loose only Vin.
