# Bluetooth speaker from an old 3-way speaker

Turning a second-hand passive 3-way speaker (bought on Marktplaats) into a mains-powered Bluetooth speaker. The cabinet had no amplifier and no crossover, only bare drivers and a plus/minus input.

<img width="49%" alt="img1speaker" src="https://github.com/user-attachments/assets/d91daa5b-f481-4889-8b63-f10ef0b686fa" />
<img width="49%" alt="img2speaker" src="https://github.com/user-attachments/assets/1dcf9ee8-0377-4ddd-9641-904efd58a14f" />

## Parts

### From the original speaker
- Cabinet
- Woofer (about 16 Ω, measured about 12 Ω DC)
- Midrange (about 12 to 16 Ω, measured about 9 to 10 Ω DC)
- Piezo tweeter (reads open circuit on a multimeter, confirmed as piezo with a capacitance measurement)

### Added
- VIRE-2C100-V1.1 amplifier board (TPA3116D2, stereo, only one channel used)
- Ca-6928 Bluetooth audio module
- LM2596 buck converter to power the Bluetooth module
- 19.5 V / 2.31 A laptop charger
- 2 A fuse and an on/off switch
- 4.5 µF non-polar capacitor (midrange filter)
- 22 to 47 Ω, 2 W resistor (piezo tweeter)

## Wiring

**Power**
- Charger plus, then fuse, then switch, then split to amp VDD and LM2596 IN+.
- Charger minus goes to amp GND and LM2596 IN-.

**Bluetooth module**
- LM2596 OUT+ and OUT- power the Ca-6928 (set the buck converter to the module's supply voltage before connecting it).
- Ca-6928 LOUT to amp INL, ROUT to amp INR, AGND to amp GND.

**Speakers (amp channel L only)**
- Woofer: L+ directly.
- Midrange: L+ through the 4.5 µF capacitor.
- Piezo tweeter: L+ through the resistor (start at 47 Ω).
- All driver minus wires go to L-. Leave R+ and R- unused.

## Ideas for later

- Physical volume knob (dual 10k potentiometer)
- Coil on the woofer
- Damping material inside the cabinet
