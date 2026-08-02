---
title: Hardware
---

# Hardware

> [!IMPORTANT]
> Placeholder. Fill in from
> [harp-tech/device.hobgoblin](https://github.com/harp-tech/device.hobgoblin)
> and from the revision of the board being handed out at the workshop.

## The board

TODO: short description of the Hobgoblin — what it is built on, what it is for,
and which hardware revision this workshop uses.

TODO: add a labelled photo or pinout diagram to `images/` and reference it here:

`![Hobgoblin board](../images/hobgoblin-board.svg)`

## Connections

TODO: complete this table from the device documentation.

| Connector | Function | Notes |
| --- | --- | --- |
| USB | Power and host communication | Appears as a serial port on the host. |
| TODO | Digital inputs | |
| TODO | Digital outputs | |
| TODO | Analog inputs | |

## Registers

Harp devices expose their functionality as **registers** — numbered addresses
that can be read, written, or configured to emit events. The device's register
map is the authoritative description of what it can do.

TODO: summarise the registers used in the workshop exercises, and link to the
full register map in the device repository.

## Safety and handling

- The board is unenclosed — handle it by the edges and keep it off conductive surfaces.
- TODO: confirm voltage limits for inputs and outputs before publishing, and state
  them here explicitly. Getting this wrong destroys boards.
