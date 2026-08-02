---
title: Setup
---

# Setup

Connecting a Hobgoblin and reading from it in Bonsai.

> [!IMPORTANT]
> Placeholder. Verify each step against a real board and the current Bonsai
> Harp packages before the workshop.

## 1. Install the Harp packages

1. Open the Bonsai package manager (**Tools → Manage Packages**).
2. Install **Bonsai.Harp**.
3. TODO: confirm whether a device-specific package is needed for the Hobgoblin,
   and name it here if so.

## 2. Connect the device

1. Plug the Hobgoblin into a USB port.
2. Find the COM port it was assigned — Windows **Device Manager**, under
   **Ports (COM & LPT)**.
3. TODO: note any driver installation needed on a fresh machine.

## 3. Talk to it from Bonsai

* Insert a `Device` source (**Bonsai.Harp**).
* Set its `PortName` property to the COM port from step 2.
* Run the workflow and open the visualizer — you should see Harp messages
  arriving from the device.

TODO: add a screenshot of this workflow to `images/` and reference it here.

## 4. Check the connection

* Add a `FilterRegister` (or `Parse`) operator after the `Device` source.
* TODO: specify which register to read as a smoke test, and what a healthy
  output looks like.

## Troubleshooting

| Symptom | Likely cause |
| --- | --- |
| No COM port appears | Cable is power-only, or a driver is missing. |
| Port is listed but the workflow errors on start | Another program still holds the port — close it and retry. |
| Workflow runs but no messages arrive | TODO: fill in from testing. |

Once the device is talking, continue to the [Exercises](exercises.md).
