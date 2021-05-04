---
title: "Electrical Design"
menu: "main"
weight: "102"
---
## Electrical Design

### Power
Interestingly, the keyboards use a -9 volt VCC.

### KAR Chip

#### Keycode data

The KAR chip outputs key states on a master clock-synced parallel bus, using the pins KC1, KC2, KC3 and KC4.

Key data is sent in a packet containing 22 frames, each of which can be represented by a 4 bit nibble.

Each packet starts with all pins high (`F`), followed by a state frame, then 10 key states.
This is what limits the keyboard to 10 notes of polyphony.

The first nibble of each note indicates the octave of the note, and whether the key is still pressed.

The second nibble represents the note within the octave block.

