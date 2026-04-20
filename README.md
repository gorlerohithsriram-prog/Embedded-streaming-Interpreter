# Embedded Streaming Interpreter

The purpose of the Embedded Streaming Interpreter (EmbStrIn) project
is to build a framework that can be used to orchestrate, distribute and run
'jobs' on embedded development kits and boards. The project is inspired by the
likes of OpenCL and CUDA.

The basic idea of this project is to let the user run kernels across a
heterogenous setup of embedded devices connected to a host computer via USB.
Currently, we plan to support the XIAO ESP32C6 and MAXIM78000FTHR boards,
keeping in mind a future goal to create a vendor agnostic framework where the
user can create their own interfaces between the devices.

The project will focus majorly on tasks mentioned below.
For a more detailed requirements specification, check out REQUIREMENTS.md

- Resource Constraints
    - Determining suitable tasks for each kind of development board
    - Quantifying performance and device stress to be used in scheduling of
    kernels

- Communication
    - Creating a protocol that will be used to send and receive packets of
    instructions, data and metadata
    - Creating an Intermediate Representation (IR) that can capture semantics of
    instructions and data development boards

- Scheduling
    - Designing and developing scheduling algorithms that will determine the 
    placement of kernels across devices
    - Designing mini-schedulers that can run on the devices in case multiple
    kernels are allowed to be issued at a time

- Infrastructure
    - Creating suitable data structures that can keep track of information
    related to the host, devices and the links.
    - Identifying algorithms that that can be used to keep track of the
    topology of the connected devices.
    - Creating firmware that runs on the development boards and interface with
    the host device at a logical level.
    - Developing host side software that can keep track of the state of the
    devices and the tasks running on each device.
    - Allowing debugging information of the host and devices to be accessed
    via a suitable logging format.