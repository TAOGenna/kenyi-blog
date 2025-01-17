+++
title = 'Radio-over-Fiber System with Passive Carrier-to-Sideband Reduction'
date = 2023-12-26T11:31:18-05:00
draft = true
categories = ["math"]
+++

<span style="color:rgb(39, 109, 223);">\[TODO: add figures\]</span>

## Problem

Design a system that implements a Radio-over-Fiber (RoF) link with 3 channels, employing single sideband modulation with an optical carrier. Use a passive filtering technique to reduce the Carrier-to-Sideband Ratio (CSR) in order to improve the link performance. The optical carrier frequencies must be separated by 0.4 nm (50 GHz), and the RF carriers must be within the range of 18 GHz to 28 GHz. The data transmission rate for each channel should be 2.5 Gb/s, using NRZ PAM-2 modulation format. The system corresponds to a 20 km fiber-optic link.

- Analyze the spectral response of the system in both the electrical and optical domains.
- Verify the correct operation of the system from the eye diagram after electrical demodulation.
- Analyze the system's response when no technique is used to reduce the CSR.

Next, we present what is understood from the proposed problem and general concepts of why certain components are used.

## Radio over Fiber and Photodetectors

In RoF systems, information is carried over optical fibers using modulated light (optical carriers). The modulation can encode RF signals into this light. In the receiver, the goal is to recover this RF information from the modulated light, which is done using a photodetector. Photodetectors are designed to convert optical signals into electrical signals. The mechanism by which this happens is that they absorb photons and generate an electrical current.

These optical carriers will be generated from a CW laser. They will be in the form of light at a specific wavelength (such as 1550 nm in telecommunications systems). We will use these carriers to transport the information over the optical fiber.

RF carriers, on the other hand, are electromagnetic signals at much lower frequencies (typically in the kilohertz to gigahertz range). In RoF systems, these RF signals modulate the optical carriers. The way this modulation works is that the RF signal modifies certain properties of the optical carrier, leaving a "trace" on it.

An important point to note is that photodetectors do not directly detect the optical carriers. This is because they are not designed to differentiate between optical frequencies (wavelengths). They simply convert the incident light into an electrical signal. Additionally, the frequency of the optical carrier (in the THz range for infrared light) is far beyond the bandwidth capabilities of electronic components, including photodetectors. What is converted and detected as an electrical signal is the modulation of the optical carrier, not the carrier frequency itself. Finally, this electrical signal from the photodetector contains the modulation, which is essentially the RF carrier signal.

## Generation of Subbands

Amplitude modulation of a carrier signal usually results in two reflected sidebands. To achieve this in the proposed system, a Mach-Zehnder modulator is used for sideband generation in the frequency domain. An Optisystem scheme to achieve this result is shown in Figure \ref{fig:sidebands}. We use an optical carrier of 1552.52 nm and an RF carrier of 20 GHz or approximately 0.14989 nm. Therefore, we expect to see frequency peaks at \( f_o \pm f_c = 1552.370, 1552.669 \). In Figure \ref{fig:sidebands2}, these values appear very close to the simulation results. Also, we note the difference in amplitude between the optical carrier and the amplitude of the sidebands, keeping in mind that we are on a logarithmic dBm scale.

`<inserte figurita>`

## Generation of Single Sideband

In an optical modulation system using a Mach-Zehnder modulator (MZM), it is possible to suppress one of the sidebands generated during the modulation process. This is achieved by introducing a specific phase shift in one of the arms of the MZM. Normally, this phase shift is set to \(\pi/2\) or \(-\pi/2\) radians.

The operation principle of the MZM is based on the interference of two optical waves passing through its two arms. When a radio frequency (RF) signal is applied to the modulator, the refractive index in one or both arms is altered, which produces a phase shift in the light passing through them. When these light waves recombine at the output of the MZM, the resulting interference pattern varies over time, following the pattern of the RF signal. This variation is equivalent to modulating the amplitude of the optical carrier.

`<inserte figura>`

In the scheme of the figure `<inserte figura>`, we introduce a 90° phase shift into one of the arms leading from the input to the Mach-Zehnder modulator. To observe the changes, we open the optical spectrum analyzer, see figure `<inserte figura>`. We note that the sideband at \(\lambda = 1552.669\) nm has been attenuated in amplitude, while the optical carrier and the other sideband remain mostly unaffected.

`<inserte figura>`

## Demodulation

In a Radio over Fiber (RoF) system, after the optical signal has been converted into an electrical signal by the photodetector, it is essential to perform a demodulation process to recover the original radio frequency (RF) signal. For this, a sine pulse generator of the same frequency as the RF signal used during the modulation stage at the beginning of the system is employed.

The reason for using a sine pulse generator with the same frequency lies in the demodulation method employed, commonly known as mixing or homodyne detection. In this process, the electrical signal obtained from the photodetector, which contains the information of the modulated RF signal, is mixed with a locally generated reference signal that has the same frequency as the original RF signal. When these two signals are mixed, constructive and destructive interference occurs, resulting in the extraction of the modulated RF signal's information.

The accuracy of the sine pulse generator's frequency is crucial for the success of the demodulation. If the frequency of the sine pulse generator does not exactly match the original RF signal's frequency, the interference will not be optimal, leading to inefficient recovery of the information and, consequently, degradation of the demodulated signal. If an eye diagram measurement is made, large differences will be seen if we use frequencies that do not exactly match, meaning the demodulation will not coincide with the originally transmitted signal.

`<inserte figura>`

In the figure `<inserte figura>`, the components used for demodulation are shown for a **single-channel system**. The low-pass filter allows us to ignore the higher frequencies, leaving only the envelope of the signal. Finally, the comparison is made through the eye diagram between the demodulated signal and the originally transmitted signal, see figure `<inserte figura>`.

`<inserte figura>`

## Complete System with 3 Channels

To build the 3-channel system, we multiplex three blocks as shown in figure `<inserte figura>`. At the output of the multiplexer, we will have three optical carriers, each corresponding to two subbands, with one of them already attenuated. Therefore, in terms of power, it can be ignored, see figure `<inserte figura>`. The system diagram presented in figure `<inserte figura>` includes the signal generation part, filters for optical carrier attenuation, and finally, the demodulation of the electrical signal.

### System with 2 Channels

As a test, a two-channel system was initially set up. The diagram is shown in figure `<inserte figura>`. For both channels, the eye diagram is also presented to verify that the signal is being correctly demodulated, see figures `<inserte figura>` and `<inserte figura>`.


