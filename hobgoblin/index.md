---
title: Hobgoblin
---

# Hobgoblin

The practical sessions use the **Harp Hobgoblin**, a small general-purpose
[Harp](https://harp-tech.org) device for interfacing a computer with the physical
world — reading sensors, driving actuators, and timestamping both against a
common clock.

Source and documentation for the device live at
[harp-tech/device.hobgoblin](https://github.com/harp-tech/device.hobgoblin).

> [!IMPORTANT]
> This section is a placeholder structure. The pages below need filling in from
> the device repository and from the boards we actually hand out on the day —
> every **TODO** marks something that must be confirmed rather than guessed.

## In this section

- **[Hardware](hardware.md)** — what is on the board and what you can plug into it.
- **[Setup](setup.md)** — connecting the device and talking to it from Bonsai.
- **[Exercises](exercises.md)** — hands-on exercises using the device.

## Why Harp?

Bonsai can already talk to plenty of hardware, but timing is the hard part of any
behavioural experiment. Harp devices timestamp every event they produce against a
shared hardware clock, so data from several devices can be aligned after the fact
without relying on when the host computer happened to see each message.

The Hobgoblin packages that behaviour into one inexpensive board, which makes it
a good fit for teaching and for prototyping a rig before committing to
purpose-built hardware.

## What you should receive

When attending this workshop you should receive:

* 1x Harp Hobgoblin board
* 1x USB cable
* TODO: confirm the final kit contents — sensors, jumpers, LEDs, and any
  breakout or expansion board handed out with the device.
