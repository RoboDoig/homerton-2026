---
title: Exercises
---

# Exercises

Hands-on exercises using the Hobgoblin. These assume you have completed
[Setup](setup.md) and can see Harp messages arriving in Bonsai.

> [!IMPORTANT]
> Placeholder exercises sketching the intended progression. Each one needs to be
> built and tested on real hardware, then written up with a workflow figure.

## Reading from the world

### **Exercise 1:** Reading a digital input

* TODO: wire a button or switch to a digital input.
* Filter the `Device` output for the digital input register.
* Visualize the result and confirm the value changes as you press the button.

### **Exercise 2:** Reading an analog input

* TODO: wire an analog sensor.
* Filter for the analog input register and plot the values over time.
* **Question:** at what rate is the device sending these samples?

## Writing to the world

### **Exercise 3:** Driving a digital output

* TODO: wire an LED to a digital output.
* Use a `Timer` and a `CreateMessage` operator to toggle the output.
* Confirm the LED blinks at the expected rate.

## Closing the loop

### **Exercise 4:** Trigger an output from an input

* Combine Exercises 1 and 3: when the button is pressed, turn the LED on.
* Measure how long the round trip takes using the device's timestamps.
* **Question:** which parts of that latency are the device, and which are the host?

### **Exercise 5:** Trigger an output from video

* Take the tracking workflow from
  [Worksheet 2](../worksheets/02-acquisition.md) and use the tracked position to
  drive a Hobgoblin output when the object enters a region of interest.

## Synchronisation

### **Exercise 6 (Optional):** Aligning device and camera data

* Log both the Harp messages and the camera frames to file.
* Align the two streams offline using the Harp timestamps.
* **Question:** why is the device timestamp more trustworthy than the time the
  host received the message?
