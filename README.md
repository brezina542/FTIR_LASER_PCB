# Custom FTIR Spectrometer – PCB Design Overview

This repository contains the design files and documentation for a **custom FTIR (Fourier Transform Infrared) spectrometer** project. The goal is to build a fully integrated system capable of precise interference measurements using a moving mirror, a photodiode sensor, and an STM32H7 microcontroller. This PCB is one of three boards in the overall system and focuses on control and signal acquisition.

---

## Project Context

Fourier Transform Infrared (FTIR) spectrometers work by splitting a laser beam, sending part of it to a **moving mirror**, and then recombining the beams to create an interference pattern. As the mirror moves, constructive and destructive interference occurs, producing a sine-like output at the photodiode. By recording this interference over a range of mirror positions, the system can construct an **interferogram**, which is used to derive spectral information.

### Key Components

- **Moving Mirror & Voice Coil**  
  A linear voice coil driver moves the mirror in precise increments. By reversing the polarity of the drive signal, the mirror can move in both directions.
- **Laser & Photodiode**  
  A laser beam passes through a beam splitter; the resulting interference is captured by the photodiode. The photodiode output typically ranges up to ~10 kHz in this design.
- **STM32H7 Microcontroller**  
  Acts as the primary controller, collecting data, driving the mirror, and interfacing with other boards in the system.
- **24-bit ADC**  
  Digitizes the photodiode signal at high resolution, ensuring minimal noise and accurate measurement of the interference waveform.
- **Comparator Array**  
  Five comparators, each set at a unique trigger level, provide additional position-tracking signals by detecting specific points on the photodiode’s sine wave.

