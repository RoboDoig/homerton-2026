---
title: Hobgoblin
---

# Hobgoblin

The practical sessions use the **Harp Hobgoblin**, a simple multi-purpose device designed
for learning the fundamentals of the [Harp](https://harp-tech.org) ecosystem. It is a
Raspberry Pi Pico 2 carrying a
[Gravity: Expansion Board](https://www.dfrobot.com/product-2393.html), so sensors and
actuators plug into labelled connectors instead of being wired to bare pins. Source and
documentation for the device live at
[harp-tech/device.hobgoblin](https://github.com/harp-tech/device.hobgoblin).

## Why Harp?

Bonsai can already talk to plenty of hardware, but timing is the hard part of any
behavioural experiment. A Harp device timestamps every event it produces against its own
hardware clock, so data from several devices can be aligned after the fact without relying
on when the host computer happened to see each message. You will use those timestamps
directly in the [Data Synchronization](../worksheets/04-synching.md) worksheet to measure a
reaction time that owes nothing to host timing.

The Hobgoblin packages that behaviour into one inexpensive board, which makes it a good
fit for teaching and for prototyping a rig before committing to purpose-built hardware.

## Registers

Everything a Harp device can do is exposed through **registers**. It is easiest to think of
a register as an individual data channel: a numbered address holding one specific kind of
information, which you can read from, write to, or receive events from as its value
changes.

The Hobgoblin's channels include, among others:

| Register | What it carries |
| --- | --- |
| `DigitalInputState` | the state of all digital input pins, reported whenever any of them changes |
| `DigitalOutputSet` | write here to raise one or more digital outputs |
| `DigitalOutputClear` | write here to lower them again |
| `AnalogData` | analog input samples |

Two consequences of this design come up repeatedly in the worksheets. First, inputs arrive
grouped: a single `DigitalInputState` message describes *every* digital pin, so reading one
button means picking its bit out of the message. Second, raising and lowering an output are
two separate channels rather than one writable value, which is why workflows that invert a
signal send a `DigitalOutputSet` message down one branch and a `DigitalOutputClear` message
down another.

Each register also has a `Timestamped` variant, which pairs the value with the device time
at which it was recorded. In Bonsai you select a channel with the `Parse` operator, and
write to one with `CreateMessage`.

## Getting started

> [!NOTE]
> Condensed from the
> [Harp Hobgoblin setup tutorial](https://harp-tech.org/tutorials/hobgoblin-setup.html),
> which also covers reading the device from Python — not needed for this workshop.

### Install the software

1. Install [Bonsai](https://bonsai-rx.org/docs/articles/installation.html).
2. Install the `Harp.Hobgoblin` package by searching for it in the
   [Bonsai package manager](https://bonsai-rx.org/docs/articles/packages.html)
   (**Tools → Manage Packages**).

### Flash the firmware

1. Download the latest version of the
   [firmware](https://github.com/harp-tech/device.hobgoblin/releases/) that matches your
   Pico board.
2. Press and hold the Pico `BOOTSEL` button while you connect the device to your computer's
   USB port. The Pico will be mounted as a new flash drive.
3. Drag and drop the `.uf2` file into the drive.

The drive disappears once the file has finished copying and the board restarts running the
firmware.

### Check the device is talking

1. Find the COM port the board was assigned — on Windows, **Device Manager** under
   **Ports (COM & LPT)**.
2. In Bonsai, insert a `Device` source (from `Harp.Hobgoblin`) and set its `PortName`
   property to that port.
3. Run the workflow and open the visualizer of the `Device` node. You should see Harp
   messages arriving from the board.

If no port appears, the cable may be power-only. If the port is listed but the workflow
errors on start, another program is still holding it open.

## Wiring used in the worksheets

The exercises assume the following connections, so it is worth wiring both up before you
start:

| Component | Pin |
| --- | --- |
| Push button | `GP2` |
| LED | `GP22` |

You are now ready for the [worksheets](../worksheets/index.md), which introduce the device
alongside the Bonsai operators that drive it.
