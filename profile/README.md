# FM-1 Rust

We build firmware for the M-VAVE FM-1 synthesizer and an audio engine that can
run on other embedded hardware.

## [fm1-rust][bsp]

The `fm1` crate is the FM-1’s bare-metal Rust board support package (BSP).
Its companion crates handle stereo audio, front-panel controls, graphics, and
real-time scheduling. If you’re writing your own firmware, the
[waveform example][waveform] shows how to turn a keypress into a tone and draw
the same samples on the LCD.

## [WaveGraph][wavegraph]

WaveGraph is a general-purpose embedded Rust DSP engine inspired by Pure Data.
A patch connects objects with cords that carry audio signals or timed messages.
The engine runs compiled patches without `std` or a heap allocator.

The [`wavegraph-fm1` app][app] pairs WaveGraph’s instruments and effects with
the audio, controls, and display drivers from `fm1-rust`. Press **PLAY** to
hear two TB-303 basslines over TR-808 and TR-909 drums. Turn the first knob
to sweep the bass filter and watch the waveform change on the FM-1’s screen.

[![WaveGraph’s TB-303 controls and live oscilloscope on the FM-1 display][scope]][demo]

[Try WaveGraph in your browser][demo]

[bsp]: https://github.com/fm1-rust/fm1-rust
[waveform]: https://github.com/fm1-rust/fm1-rust/blob/main/fm1-rticx/examples/rticx-waveform.rs
[wavegraph]: https://github.com/fm1-rust/wavegraph
[app]: https://github.com/fm1-rust/wavegraph/tree/main/wavegraph-fm1
[scope]: https://raw.githubusercontent.com/fm1-rust/wavegraph/main/wavegraph-fm1/assets/tb-303.png
[demo]: https://wavegraph.org/
