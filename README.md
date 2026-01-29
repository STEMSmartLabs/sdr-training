# SDR Training Flowgraphs (GNU Radio)

A small collection of **software-defined radio (SDR)** training examples built with **GNU Radio Companion (GRC)**. This repo includes ready-to-open `.grc` flowgraphs for common SDR tasks (FM receive, spectrum analysis, loopback testing, Doppler radar), plus a quick getting started PDF.

## Contents

- **GettingStartedGuide.pdf**  
  Intro / setup guide for running the examples (install notes, basic workflow, and tips).

- **RTL_SDR_FM.grc**  
  FM broadcast receiver flowgraph designed for **RTL-SDR** dongles (tuning, demodulation, and audio output).

- **USRP_SpectrumAnalyzer.grc**  
  Spectrum analyzer-style flowgraph intended for **Ettus USRP** devices (visualizing RF spectrum in real time).

- **Pluto_Loopback.grc**  
  Basic **ADALM-Pluto** loopback test to validate TX/RX path, sample rates, and gain settings.

- **Pluto_Doppler_RADAR.grc**  
  A simple Doppler radar demonstration using **ADALM-Pluto** (useful for motion detection experiments and DSP learning).

## Requirements

- **GNU Radio** (with GNU Radio Companion)
- Hardware (depending on the flowgraph you run):
  - **RTL-SDR** (for `RTL_SDR_FM.grc`)
  - **ADALM-Pluto (PlutoSDR)** (for `Pluto_*`)
  - **Ettus USRP** (for `USRP_SpectrumAnalyzer.grc`)
- Appropriate drivers / device support:
  - RTL-SDR drivers (e.g., `librtlsdr`)
  - PlutoSDR via `libiio` / Pluto support
  - UHD for USRP

## Quick Start

1. Install GNU Radio and confirm your SDR is recognized by the OS.
2. Clone this repo:

   ```bash
   git clone <your-repo-url>
   cd sdr-training
3. Open a flowgraph in GNU Radio Companion:

    gnuradio-companion RTL_SDR_FM.grc
4. In GRC:
    Verify device parameters (sample rate, center frequency, gains)
    Click Run ▶️

## Flowgraph Notes

## RTL_SDR_FM.grc
- Tune to a local FM station (e.g., 88–108 MHz).
- If audio is distorted, reduce RF gain or adjust deemphasis / resampler settings.

## USRP_SpectrumAnalyzer.grc
- Set the correct UHD device string if needed.
- Ensure your sample rate and bandwidth are within your USRP’s capabilities.

## Pluto_Loopback.grc
- Useful for first-time validation of Pluto configuration.
- Start with conservative gains to avoid clipping.

## Pluto_Doppler_RADAR.grc
- Intended for learning and experimentation.
- Doppler setups can be sensitive to gain, leakage, and environment—expect to tweak parameters.

## Troubleshooting
- No device found: confirm drivers, permissions, and that no other app is using the SDR.
- XRUNs / stuttering: lower sample rate, reduce GUI load (fewer FFT points), or increase buffers.
- Overload / clipping: reduce gain and check signal levels throughout the chain.

## Contributing
PRs are welcome—especially improvements to:
- Default parameter values
- Comments inside flowgraphs
- Additional training examples (AM, SSB, ADS-B, IQ recording/playback, etc.)

## License
This project is licensed under the MIT License.



