# Modulation Comparison
Overview over the modulation measurements.

We, in principle, have three modulation sources:
 + Direct AC modulation (capacitor in parallel to current output)
 + Direct DC modulation (modulation circuit in parallel to current output)
 + JFET DC modulation (bias claw JFET modulation circuit in parallel to current output)

All these modulations can be applied with different output stages:
 + Direct output stage: drain output of pass MOSFET to load
 + 10uH output inductor after drain output of pass MOSFET
 + 100uH output inductor after drain output of pass MOSFET

The direct output is set by default. To solder the inductors,
a solder jumper must be cut.

Each step shall thus make following  measurements:
 + A noise measurement @ 200mA
 + A transfer function measurement
 + Turn-on curve to 100mA
 + Turn-off curve from 100mA


## Measurement Parameters
Modulations are tested against a ~10Ohm resistor

If not used: the AC-Mod Floating

If not used: DC-Mod Floating

If not used: JFET: !!!TBD!!!

Noise ASD: 10 MSps measurement rate for two seconds. Modulation input is held at 0mV.
Current Noise Amplifier v0.5 with 50 Ohm termination at Moku:Pro input.

Transfer function: 1Hz up to 500MHz with 1024 logarithmically space samples. Amplitude is 100mVpp 50R0 output

Turn on&off: 20 second recordings with 1MSps against a 12.870Ohm resistor.

## Measurement Checklist

This is the checklist (❌⚙️⚠️✅) to keep track of modulation transfer function measurements

| Output         | AC Modulation       | DC Modulation        | JFET DC Modulation  |
| :------------- | :------------------ | :------------------- | :------------------ |
| Direct Output  | 2026-11-04 15:53 ✅ | 2026-11-04 15:59 ✅ | 2026-11-04 16:55 ✅ |
| 10uH Inductor  | 2026-11-04 18:1Y ✅ | 2026-11-04 18:14 ✅ | 2026-11-04 16:YY ✅ |
| 100uH Inductor | 2026-11-05 10:54 ✅ | 2026-11-05 10:57 ✅ | 2026-11-05 11:45 ✅ |
| 150uH Inductor | 2026-11-05 13:57 ✅ | 2026-11-05 14:00 ✅ | 2026-11-05 12:14 ✅ |

This is the checklist (❌⚙️⚠️✅) to keep track of noise ASD measurements

| Output         | AC Modulation       | DC Modulation        | JFET DC Modulation  |
| :------------- | :------------------ | :------------------- | :------------------ |
| Direct Output  | 2026-11-04 16:12 ✅ | 2026-11-04 16:08 ✅ | 2026-11-04 16:51 ✅ |
| 10uH Inductor  | 2026-11-04 18:05 ✅ | 2026-11-04 18:09 ✅ | 2026-11-04 17:37 ✅ |
| 100uH Inductor | 2026-11-05 11:21 ✅ | 2026-11-05 11:17 ✅ | 2026-11-05 11:52 ✅ |
| 150uH Inductor | 2026-11-05 14:11 ✅ | 2026-11-05 14:07 ✅ | 2026-11-05 12:21 ✅ |

This is the checklist (❌⚙️⚠️✅) to keep track of Turn on/off measurements

| Output         | Type               | Measurement ULNDLDD | Measurement ULNDLDD JFET | Measurement ULNDLDD Mini | Measurement ULNDLDD Mini Switch |
| :------------- | -----------------: | :------------------ | :----------------------- | :----------------------- | :-----------------------------  |
| Direct Output  | Turn On/Off Curve  | 2026-11-04 10:52 ✅ | 2026-11-04 16:27 ✅     | 2026-11-04 10:48 ✅      | 2026-11-04 12:16 ✅            |
| 10uH Inductor  | Turn On/Off Curve  | 2026-11-04 17:59 ✅ | 2026-11-04 17:40 ✅     | 2026-11-04 11:20 ✅      | 2026-11-04 11:38 ✅            |
| 100uH Inductor | Turn On/Off Curve  | 2026-11-05 10:45 ✅ | 2026-11-05 11:40 ✅     | 2026-11-04 11:51 ✅      | 2026-11-04 11:50 ✅            |
| 150uH Inductor | Turn On/Off Curve  | 2026-11-05 13:53 ✅ | 2026-11-05 12:09 ✅     | 2026-11-04 12:06 ✅      | 2026-11-04 12:04 ✅            |

Single Measurement Quickview Checklists:

### Transfer Functions
 + 12.87Ohm termination resistance on driver
 + Moku Input 4Vpp, 1MOhm, DC
 + Relevant Mod input connected, others floating
 + Driver output current ~ 100mA -> 1.287V
 + Transfer Function 1Hz to 500MHz 1024 Log spaced samples
 + Mod Amplitude 100mVpp, 50Ohm output
 + Data Logger Filename "ULNLDD-"~~(Direct|10u|100u|150u)~~"-"~~(AC|DC|JFET)~~"-TF"

### Noise ASDs
 + Connection to CNA v0.5
 + Moku Input 400mVpp, 50Ohm, DC
 + Relevant Mod input connected, others floating
 + Mod Amplitude 0V DC, 50Ohm output
 + Driver output current ~ 100mA -> 1.287V
 + 10 MSps, 2s
 + Data Logger Filename "ULNLDD-"~~(Direct|10u|100u|150u)~~"-"~~(AC|DC|JFET)~~"-NF"

### Turn On/Off Curves
 + Right driver voltages
 + 12.87Ohm termination resistance on driver
 + Moku input 4Vpp, 1MOhm, DC
 + Driver mod inputs floating
 + Driver output current ~ 100mA -> 1.287V
 + Switch of Mini Driver set to right position
 + 1 MSps (998.4kSps), 20s; 5s Start, 15s End
 + Data Logger Filename "ULNLDD"~~(Mini|MiniSwitch|JFET|"")~~"-"~~(Direct|10u|100u|150u)~~"-TurnOnOff"