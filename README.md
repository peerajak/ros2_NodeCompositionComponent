# Unit 8   Node Composition
The ROS2 programs (nodes) you create are compiled into executables that you can then execute, either directly or using a launch file. However, this method has a limitation: each executable will run in one process.

What does this mean? This means that you cannot run more than one ROS node in a single process. Thankfully, ROS2 provides components. So, what are components?

## 8.1   What are ROS2 Components?
Components are the equivalent in ROS2 to well-known ROS1 nodelets. By writing your program as a component, you can build it into a shared library instead of an executable. This allows you to load multiple components into a single process. Quite interesting, right?

There are 2 main approaches on how to use components:

Run-time composition: Run-time composition allows the configuration and behavior of the robotic system to be modified or extended while the system is running. Components can be dynamically added, removed, or reconfigured without stopping the entire system.

Compile-time composition: Compile-time composition involves specifying the system configuration at the time of compiling the code. This means that the structure and behavior of the robotic system are determined before the code is compiled into an executable.

When choosing between compile-time and run-time composition, it's essential to weigh the pros and cons. Compile-time composition often provides superior performance and simplified debugging due to its fully defined and optimized composite object. On the other hand, runtime composition offers greater flexibility and adaptability because the composite object can be dynamically created and modified during program execution.

Let's start by checking an example of run-time composition.#