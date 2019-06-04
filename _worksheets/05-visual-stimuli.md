---
layout: worksheet
title: Visual Stimuli
permalink: /worksheets/visual-stimuli/
---


The exercises below will show you how to  translate the above diagram of states and events into an equivalent Bonsai workflow, which can be easily adapted and modified to describe many different operant behaviour tasks.

### **Exercise 1:** Sinewave Gratings

In this worksheet, we will be using an Arduino or a camera as an interface to detect external behaviour events. For experimental purposes, it is very helpful to record and timestamp _all_ of these events, independently of which state the task is in.

* Connect a digital sensor (e.g. beam-break, button, TTL) into Arduino pin 8.
* Insert a `DigitalInput` source and set it to Arduino pin 8.
* Insert a `Timestamp` combinator.
* Insert a `CsvWriter` sink and configure its `FileName` property with a file name ending in `.csv`.
* Run the workflow and activate the digital sensor a couple of times. Stop the workflow and confirm that the events were successfully timestamped and logged in the `.csv` file.

### **Exercise 2:** Looming Stimulus

Translating a state machine diagram into a Bonsai workflow begins by identifying the initial state of the task (i.e. the beginning of each trial). It is often convenient to consider the inter-trial interval period as the initial state, followed by stimulus presentation.

* Insert a `Timer` source and set its `DueTime` property to be about 3 seconds.
* Insert a `Sink` operator and set its `Name` property to `StimulusOn`.
* Double-click on the `Sink` node to open up its internal specification.

The `Sink` operator allows you to specify arbitrary processing side-effects without affecting the original flow of events. It is often used to trigger and control stimulus presentation in response to events in the task. Inside the internal specification, `Source1` represents input events arriving at the sink. In the specific case of `Sink` operators, the `WorkflowOutput` node can be safely ignored.

* Insert a `Boolean` operator following `Source1` and set its `Value` property to `True`.
* Insert a `DigitalOutput` sink and connect it to Arduino pin 13.
* Run the workflow a couple of times and verify that the sequence of events is progressing correctly.

**Note:** Opening a new connection to the Arduino can take several seconds due to the way the Firmata protocol is implemented. This may introduce a slight delay in starting the task. This delay is only present at the start of the workflow and will not affect the behavior of the state machine.
{: .notice--info}

* In the main top-level workflow, insert a `Delay` operator and set its `DueTime` property to a couple of seconds.
* Copy the `StimulusOn` operator and insert it after the `Delay` (you can either copy-paste or recreate it from scratch).
* Rename the new operator to `StimulusOff` and double-click it to open up its internal representation.
* Set the `Value` property of the `Boolean` operator to `False`.
* Run the workflow a couple of times. Is it behaving as you would expect?
* Insert a `Repeat` operator after the `StimulusOff`.
* Run the worklow. Can you describe in your own words what is happening?
* **Optional:** Draw a marble diagram for `Timer`, `StimulusOn`, `Delay`, and `Repeat`.

### **Exercise 3:** Presenting a sequence of stimuli

* Delete the `Delay` operator.
* Insert a `SelectMany` operator after `StimulusOn`, and set its `Name` property to `Response`.
* Double-click on the `SelectMany` node to open up its internal specification.

The `SelectMany` operator is used here to create a new state for every input event. `Source1` represents the input event that created the state, and `WorkflowOutput` will be used to report the end result from the state (e.g. whether the response was a success or failure).

* Insert a `DigitalInput` source and set it to Arduino pin 8.
* Insert a `Take` operator and set its `Count` property to 1.
* Insert a `Boolean` operator and set its `Value` property to `True`.
* Delete the `Source1` operator.
* Connect the `Boolean` operator to `WorkflowOutput`.
* Run the workflow a couple of times. Is it behaving as you would expect?

### **Exercise 4:** Randomizing  and choice

* Still inside the `SelectMany`, insert a `Timer` source and set its `DueTime` property to be about 1 second.
* Insert a `Boolean` operator and set its `Value` property to `False`.
* Insert the `Amb` combinator and connect to it both of the `Boolean` operators.
* Connect the output of `Amb` to `WorkflowOutput`.
* Run the workflow a couple of times, open the visualizer of the `Response` node, and describe what is being plotted.

### **Exercise 5:** Presenting 3D visual stimuli

* Insert a `Condition` operator after the `StimulusOff` node, and set its `Name` property to `Success`.

* Insert another `Condition` operator in a new branch off the `StimulusOff` node, and set its `Name` property to `Miss`.
* Double-click on the `Condition` operator to open up its internal specification.
* Insert a `BitwiseNot` operator after `Source1`.

* In the top-level workflow, insert a `Merge` operator and connect to it the outputs of both conditional branches.

### **Exercise 6 (Optional):** Map 2D stimuli onto 3D objects

### **Exercise 7 (Optional):** Closed-loop control of perspective
