---
title: Acquisition and Tracking
---

# Acquisition and Tracking

Bonsai can acquire and record data from many different devices. These exercises
introduce the most common Bonsai data types, starting with images.

## Video acquisition

An image is a 2D matrix of pixels. Each pixel is either a brightness value in a
grayscale image, or a BGR colour value in a colour image.

### **Exercise 1:** Saving a video

* Insert a `CameraCapture` source.
* Insert a `VideoWriter` sink.
* Configure the `FileName` property of `VideoWriter` with a name ending in `.avi`.
* Run the workflow and check that it produces a valid video file.

### **Exercise 2:** Saving a grayscale video

* Insert a `Grayscale` transform between `CameraCapture` and `VideoWriter`.
* Run the workflow — the output should now be a grayscale movie.
* Modify the workflow so that it records a colour **and** a grayscale movie
  simultaneously.

## Audio acquisition

Audio is sampled far faster than video, and arrives in buffered chunks of many
samples. Multi-channel buffers are represented as a 2D matrix where rows are
channels and columns are time.

### **Exercise 3:** Saving a WAV file

* Insert an `AudioCapture` source.
* Insert an `AudioWriter` sink.
* Configure `FileName` with a name ending in `.wav`.
* Make sure the `SamplingFrequency` of `AudioWriter` matches the capture rate.
* Run for a few seconds and play the file back to check it is valid.

## Tracking

### **Exercise 4:** Tracking a moving object

* Start from the grayscale workflow in Exercise 2.
* Insert a `Threshold` transform to isolate the object from the background.
* Insert `FindContours`, then `BinaryRegionAnalysis`, then `LargestBinaryRegion`.
* Visualize the `Centroid` output while moving an object in front of the camera.

### **Exercise 5 (Optional):** Logging positions to a file

* Insert a `CsvWriter` sink after `LargestBinaryRegion`.
* Set `Selector` to `Centroid.X,Centroid.Y`.
* Run the workflow, then plot the resulting trajectory in Python or MATLAB.

> [!NOTE]
> Placeholder content adapted from the St Andrews 2024 course. Replace the
> exercises with the workshop's final material and add workflow figures.

Next: [Closed-Loop Systems](03-closed-loop.md). To bring in real hardware, see the
[Hobgoblin](../hobgoblin/index.md) section.
