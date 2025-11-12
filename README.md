# TuchAudio 101b
Discrete Phono preamp -- reedition of my very first phono preamp, circa 1987...

## Purpose
Fully symmetrical discrete op-amp phono preamp -- loosely inspirated by _Elektor_ designs. RIAA correction is achieved thru two different ways: low frequency boost is implemented on the feedback network, while the high-frequency rollof is done with a **passive low-pass filter**, for improved signal-to-noise ratio.

## Design quirks
The preamp itself is **fully DC-coupled**, for optimum bass performance; however, that means that the _input stage offset_ is **multiplied** by the low-frecuency gain (+34 dB), which may result on stage saturation. To compensate for that, each channel provides room for `R+` or `R-` resistors, connecting the inverting input (feedback) to the power rails, in case some manual adjustment is needed.

Just like the original build, a **subsonic filter** is integrated into the board. This is a **fourth-order high pass filter** (24 dB/oct) with a cutoff frequency of **11.8 Hz**; again, based on an _Elektor_ design (_Summer Circuits 1984_). However, since it is located _after_ the amplification, the high gain of the stage at low frequencies might saturate the preamp itself, in extreme cases.

DIN and RCA jacks are provided for signal input. Since the _native_ input impedance, being a symmetric op-amp design, is expected to be **extremely high**, space for suitable load (`Rx` and `Cx`) is provided for perfect adaptation; but for added flexibility, it is possible to use the free input for a suitable RC combo in parallel, to match the appropriate cartridge load.

Both direct and subsonic-filtered outputs are provided, and properly selected thru the [509 Input Selector board](). An aditional RCA **output** jack can be installed in order to use the circuit as a _stand-alone preamp_.

### Suggested mods

#### Subsonic output
As previously mentioned, both direct and subsonic outputs are provided, and selected thru the _509 Input Selector Board_; in case a non-selecting board is used (like the [501 Input Selector board]()), you can break the `JP1` and `JP2` jumpers to route the _subsonic_ output to the bus-style/RCA jack output instead (with suitable external bodge wires).

#### DC-block
While being fully DC-coupled is definitely desirable from a sound quality standpoint, it may be troublesome in some extreme cases, especially with _warped_ records. If this is a concern, adding a suitable _capacitor_ (**~100 µF**) in the feedback loop will prevent this. Just lift one pin of `R9/R109` and bodge the capacitor _in series_. **There is no need to use `R+/R-`** in that case, and you should remove them in order to check the _offset polarity_; mount the extra capacitor consequently.

## Specs

- **Power Supply:** +/- 9 V (symmetrical), just a few mA.
- **Gain at 1 kHz:** x50 (+34 dB)
- **Input sensitivity:** 3.6 mV (for 180 mV output)
- **Input impedance:** determined by `Rx/Cx`, either internal or external.
- **Output level and impedance:** 180 mV / 1 KΩ
- **Overload margin:** at least +15 dB
- **Signal-to-noise ratio:** more than 80 dB (estimated)
- **Distortion:** TBD
