# tlc-strummer
USB MIDI chord strummer for Teensy LC

Simple chord strummer with a 8x3 (or up to a full 12x3) keyboard based on the circle of fifths, like the Omnichord. For strumming the chords, a set of eight touch sensitive pads, strings or similar is used. In my build I simply used a 90 deg pin header for touch electrodes.

With an 8x3 keyboard setup using 6x6 mm tact switches, it all fits on a 7x5 cm perfboard.

Chords are selected as follows:

Columns from left to right selects the key
Bb, F, C, G, D, A, E, B

Rows select the kind of chord you play
top row     - major,
mid row     - minor,
bottom row  - 7th

Additional chord combinations are
top+bottom  - major 7th,
mid+bottom  - minor 7th,
top+mid     - diminished,
all three   - augmented

How to use:

Connect USB to computer or other host device with a midi synth software installed and running. 

Select "Teensy MIDI" as MIDI input in synth software if necessary.

Press and hold chord buttons and strum with a finger over the touch pads to play.


Upgrade to built in audio!

For additional built in audio output, you can use a Teensy 3.2 and the t32-strummer-ah.ino sketch. It will output a Karplus-Strong algorithm generated plucked string sound on the Teensy 3.2 DAC pin (A14). Surprisingly authentic sounding to an autoharp :) For the more Omnichord oriented audience, there is a t32-strummer-oc.ino sketch that will fit better.

Connect the Teensy 3.2 DAC output to an amplifier via a 10uF capacitor to filter out DC component (positive pin to A14 pin, negative pin to amplifier positive input, teensy gnd to amplifier negative input). If you are using an amp module with built in input capacitor, you could leave it out.

Note that the DAC output pin is not in itself capable of driving speakers or headphones.