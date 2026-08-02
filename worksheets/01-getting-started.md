---
title: Getting Started
---

# Getting Started

Install Bonsai and get comfortable with the editor. If you can, do this
**before** the workshop — downloads over conference wifi are slow.

## Installing Bonsai

1. Download the Bonsai installer from [bonsai-rx.org](https://bonsai-rx.org).
2. Run the installer and launch Bonsai.
3. Open the package manager (**Tools → Manage Packages**) and install
   **Bonsai - Starter Pack**.
4. Click the `Updates` tab and install any available upgrades.
5. Read the [editor guide](https://bonsai-rx.org/docs/articles/editor.html) for
   an introduction to the user interface.

> [!TIP]
> Bonsai runs on Windows. If you use macOS or Linux, you will need a Windows
> virtual machine — set this up in advance and tell us beforehand so we can help.

## Your first workflow

### **Exercise 1:** A stream of numbers

* Insert a `Timer` source (**Bonsai.Reactive**).
* Set its `Period` property to `00:00:00.5`.
* Run the workflow and open the visualizer by double-clicking the node.
* **Question:** what is the workflow producing, and how often?

### **Exercise 2:** Watching a stream

* Add a `Timestamp` transform after the `Timer`.
* Run the workflow again and inspect the output values.
* Stop the workflow. Note that nothing runs until you press start — a workflow
  is a *description* of a computation, not the computation itself.

## Saving and organising work

* Save the workflow as `first-workflow.bonsai` in a folder of your own.
* Bonsai writes a companion `.bonsai.layout` file storing visualizer positions.
  Keep it next to the workflow.

> [!NOTE]
> Placeholder content. Expand these exercises to match what the workshop
> actually covers, and add workflow screenshots to `images/`.

Next: [Acquisition and Tracking](02-acquisition.md).
